---
title: "Mastering User Settings in SharePoint Framework"
url: "https://devblogs.microsoft.com/microsoft365dev/mastering-user-settings-in-sharepoint-framework/"
date: "Sat, 07 Feb 2026 01:17:15 +0000"
author: "Paolo Pialorsi"
feed_url: "https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/feed/"
---
<p>User preferences and settings are fundamental components of modern web applications. When developing SharePoint Framework (SPFx) solutions, the ability to store and manage user-specific configurations across devices and sessions becomes crucial for delivering personalized experiences. This article explores a robust, enterprise-ready pattern for handling user settings in SharePoint Framework applications. There is also a <a href="https://adoption.microsoft.com/sample-solution-gallery/sample/pnp-sp-dev-spfx-web-parts-react-settings-approot/">companion sample</a> available on the <a href="https://aka.ms/community/samples">Community Sample Solution Gallery</a>.</p>
<p>You can simply download the source code of the sample and then follow this article to understand how it works.</p>
<h2>Understanding the Challenge</h2>
<h3>The Need for Persistent User Settings</h3>
<p>In SharePoint Framework development, we frequently encounter scenarios where web parts or extensions require the ability to store user-specific information, options, or preferences. Traditional client-side storage mechanisms, such as <code>localStorage</code> or <code>sessionStorage</code>, fall short when we need:</p>
<ul>
<li><strong>Cross-device synchronization</strong>: Settings available across multiple devices</li>
<li><strong>Per-user isolation</strong>: Secure storage ensuring users can only access their own settings</li>
<li><strong>Enterprise scalability</strong>: Solutions that can handle multiple web parts and applications</li>
<li><strong>Technology resilience</strong>: Independence from client-side storage limitations</li>
</ul>
<h3>Limitations of Traditional Approaches</h3>
<p>Relying solely on local user settings presents several challenges:</p>
<ol>
<li><strong>Device-specific storage</strong>: Settings remain confined to individual browser sessions</li>
<li><strong>Limited cross-application support</strong>: Difficulty sharing preferences between multiple web parts</li>
<li><strong>Security concerns</strong>: Potential exposure of sensitive user preferences</li>
<li><strong>Technology dependency</strong>: Vulnerability to changes in client-side storage technologies</li>
</ol>
<h2>Architecture Overview</h2>
<h3>Solution Components</h3>
<p>The proposed architecture leverages the Microsoft 365 ecosystem to deliver a comprehensive user settings management solution:</p>
<p><a href="https://devblogs.microsoft.com/microsoft365dev/wp-content/uploads/sites/73/2026/02/SPFx-Settings-Architectural-Diagram.webp"><img alt="Architectural diagram of the solution: the SPFx component consume securely via OAuth a backend Azure Function. The function relies on OBO (On Behalf Of) to consume Microsoft Graph and to access OneDrive for Business on behalf of the current user. All the communication flow is secured by Entra ID." class="alignnone wp-image-25281" height="297" src="https://devblogs.microsoft.com/microsoft365dev/wp-content/uploads/sites/73/2026/02/SPFx-Settings-Architectural-Diagram-300x150.webp" width="594" /></a></p>
<h3>Security Framework</h3>
<p>The solution implements enterprise-grade security through:</p>
<ul>
<li><strong>Entra ID Authentication</strong>: Leveraging Microsoft&#8217;s identity platform</li>
<li><strong>OAuth 2.0 Authorization</strong>: Secure token-based authentication</li>
<li><strong>On-Behalf-Of (OBO) Flow</strong>: Enabling the backend to act on behalf of authenticated users</li>
<li><strong>Microsoft Graph Integration</strong>: Utilizing official Microsoft APIs for data access</li>
</ul>
<h2>The Special Folder Concept</h2>
<h3>Understanding App-Specific Folders</h3>
<p>Microsoft Graph provides access to special folders in each user&#8217;s OneDrive for Business through the endpoint:</p>
<pre><code>/me/drive/special/{folderName}</code></pre>
<p>The <code>approot</code> special folder is particularly valuable for application-specific storage:</p>
<pre><code>/me/drive/special/approot</code></pre>
<p>It can be used to store files and settings specific to a particular application and user.</p>
<h3>Per-Application Isolation</h3>
<p>In fact, each Entra ID application registration receives a dedicated folder structure:</p>
<pre><code>OneDrive for Business/
└── Apps/
    └── {Application Display Name}/
        └── {User Settings Files}</code></pre>
<p>This architecture ensures:</p>
<ul>
<li><strong>Complete isolation</strong> between different applications</li>
<li><strong>Per-user storage</strong> with automatic user context</li>
<li><strong>Secure access</strong> through Microsoft Graph APIs</li>
</ul>
<h2>Implementation Deep Dive</h2>
<h3>Accessing the API from within SharePoint Framework</h3>
<p>One option that you have is to access the Microsoft Graph special folder API from within your SharePoint Framework web part or extension. It is simple and it just works.</p>
<p>However, from an architectural standpoint it is better to have a backend API taking care of security, caching, business logic, etc. to have better decoupling of code, maintenance, and monitoring of the solution. That&#8217;s why in the solution illustrated in this article we explain you the main steps to go through in order to create such an enterprise-level scenario application.</p>
<h3>Entra ID Application Configuration and permission scopes</h3>
<p>In order to being able to access an <strong>AppRoot</strong> folder via Microsoft Graph, you need to register an Entra ID application and to grant specific permissions to that app.</p>
<p>Browse to the <a href="https://entra.microsoft.com/">Microsoft Entra admin center</a>, select <strong>App Registrations</strong> and then select <strong>+ New registration</strong> in the upper left side of the screen. Provide a name for the application, select to target your current tenant only (<em>Accounts in this organizational directory only</em>), and select the <strong>Register</strong> command at the end of the registration page. You can refer to the article <a href="https://learn.microsoft.com/entra/identity-platform/quickstart-register-app">Register an application in Microsoft Entra ID</a> for further details about registering an Entra ID application.</p>
<p>Then move to the <strong>API permissions</strong> configuration panel of the new application and configure the specific <code>Files.ReadWrite.AppFolder</code> delegated permission for Microsoft Graph access. This permission enables the application to read and write files specifically within the app folder, maintaining security boundaries and under the identity of currently connected user.</p>
<p>Using a tenant admin account select the <strong>Grant admin consent for &#8230;</strong> command, to grant the selected permission to the application.</p>
<p>You can learn more about granting API permissions to an Entra ID application reading the article <a href="https://learn.microsoft.com/entra/identity-platform/quickstart-configure-app-access-web-apis">Configure app permissions for a web API</a></p>
<h3>API Exposure to SharePoint Framework</h3>
<p>To make the application accessible to SharePoint Framework web parts and extensions, you also need to expose an API in the configuration of the Entra ID application. While still in the <a href="https://entra.microsoft.com/">Microsoft Entra admin center</a>, select the <strong>Expose an API</strong> panel. Now, follow the instructions available <a href="https://learn.microsoft.com/entra/identity-platform/quickstart-configure-app-expose-web-apis">here</a> to expose a custom API with a dedicated permission scope from your application. For the sake of completeness, you can for example create a permission scope with name <code>UserSettings.Manage</code>. Keep track of the <code>Application ID URI</code> (it should look like <code>api://application-client-id</code>) value configured for the application because you will need it later.</p>
<h3>SharePoint Framework Implementation</h3>
<p>You are now ready to implement the actual SharePoint Framework web part or extension in order to access the backend API.</p>
<h4>HTTP Client Configuration</h4>
<p>The SPFx web part or extensions leverage the built-in <code>AadHttpClientFactory</code> to create authenticated HTTP clients. For example, in a web part you can create a new instance of the <code>AadHttpClient</code> using syntax like the following one and providing the object instance to the React components rendering the user experience of your customization.</p>
<pre><code class="language-typescript">import { AadHttpClient, AadHttpClientFactory } from '@microsoft/sp-http';

export default class UserSettingsWebPart extends BaseClientSideWebPart&lt;IUserSettingsWebPartProps&gt; {
  private _httpClient: AadHttpClient;

  protected async onInit(): Promise&lt;void&gt; {
    this._httpClient = await this.context.aadHttpClientFactory
      .getClient('api://application-client-id');
    
    return super.onInit();
  }

  public render(): void {
    const element: React.ReactElement&lt;IUserSettingsProps&gt; = React.createElement(
      UserSettings,
      {
        httpClient: this._httpClient,
        apiUrl: this.properties.apiUrl
      }
    );

    ReactDom.render(element, this.domElement);
  }
}</code></pre>
<p>In the above code excerpt, the value of <code>api://application-client-id</code> needs to be the Application ID URI that you configured while exposing an API from within the Entra ID application.</p>
<p>You can find additional details about securely consuming a REST API in SharePoint Framework reading the article <a href="https://learn.microsoft.com/sharepoint/dev/spfx/use-aadhttpclient">Connect to Entra ID-secured APIs in SharePoint Framework solutions</a>.</p>
<h4>Consuming the Backend API</h4>
<p>Once you have the <code>AadHttpClient</code> instance, you can use it to consume the Azure Function REST endpoints. The methods of the <code>AadHttpClient</code> class allow you to make authenticated HTTP requests to the backend API. Here&#8217;s an example of how to implement the CRUD operations in your React component:</p>
<pre><code class="language-typescript">const fetchSettings = async (): Promise =&gt; {
  if (!aadHttpClient) return;
  setLoading(true);
  setMessage('');
  try {
    const res = await aadHttpClient.get(apiUrl, AadHttpClient.configurations.v1);
    if (!res.ok) throw new Error('Failed to list settings');
    const data = await res.json();
    setSettings(Array.isArray(data) ? data : []);
  } catch (err) {
    setMessage((err as Error).message);
  } finally {
    setLoading(false);
  }
};

const handleAdd = async (): Promise =&gt; {
  if (!aadHttpClient || !key) return;
  setLoading(true);
  setMessage('');
  try {
    const res = await aadHttpClient.fetch(`${apiUrl}/${encodeURIComponent(key)}`, AadHttpClient.configurations.v1, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(value)
    });
    if (!res.ok) throw new Error('Failed to add setting');
    setKey('');
    setValue('');
    await fetchSettings();
  } catch (err) {
    setMessage((err as Error).message);
  } finally {
    setLoading(false);
  }
};

const handleUpdate = async (): Promise =&gt; {
  if (!aadHttpClient || !editKey) return;
  setLoading(true);
  setMessage('');
  try {
    const res = await aadHttpClient.fetch(`${apiUrl}/${encodeURIComponent(editKey)}`, AadHttpClient.configurations.v1, {
      method: 'PUT',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(value)
    });
    if (!res.ok) throw new Error('Failed to update setting');
    setEditKey(null);
    setKey('');
    setValue('');
    await fetchSettings();
  } catch (err) {
    setMessage((err as Error).message);
  } finally {
    setLoading(false);
  }
};

const handleRemove = async (removeKey: string): Promise =&gt; {
  if (!aadHttpClient) return;
  setLoading(true);
  setMessage('');
  try {
    const res = await aadHttpClient.fetch(`${apiUrl}/${encodeURIComponent(removeKey)}`, AadHttpClient.configurations.v1, {
      method: 'DELETE'
    });
    if (!res.ok) throw new Error('Failed to remove setting');
    await fetchSettings();
  } catch (err) {
    setMessage((err as Error).message);
  } finally {
    setLoading(false);
  }
};</code></pre>
<p>In the code above, the <code>AadHttpClient.configurations.v1</code> configuration ensures that the client automatically includes the OAuth access token in the <code>Authorization</code> header of each request. The <code>apiUrl</code> parameter is the base URL of your Azure Function endpoint, and the key is appended to the URL to identify the specific setting to manage.</p>
<h4>Web API Permissions Declaration</h4>
<p>However, in order to being able to consume the custom API from SharePoint Framework, you also need to customize the <code>package-solution.json</code> file of the SharePoint Framework solution. In fact, you need to declare the required permissions to consume your custom API:</p>
<pre><code class="language-json">{
  "solution": {
    "webApiPermissionRequests": [
      {
        "resource": "your-application-display-name",
        "scope": "UserSettings.Manage"
      }
    ]
  }
}</code></pre>
<p>Where the value of the <code>resource</code> attribute is the name of the application that you registered in Entra ID, while the value of the <code>scope</code> attribute is the name you gave to the permission scope that you registered while exposing an API with your Entra ID application.</p>
<h3>Azure Function Backend Implementation</h3>
<p>Now that SharePoint Framework can securely consume your back-end API, you need to implement the actual API. In this section we will focus only on key features like authentication, token validation, and consumption of Microsoft Graph on behalf of the current user.</p>
<h4>Token Validation and OBO Flow</h4>
<p>The Azure Function implements secure token validation through an open source library created by <a href="https://github.com/waldekmastykarz">Waldek Mastykarz</a>. You can find the implementation of the token validation logic <a href="https://github.com/pnp/sp-dev-fx-webparts/blob/main/samples/react-settings-approot/back-end/src/functions/userSettings.ts#L135">here</a> on the GitHub repository of the sample solution associated with this article. Right after validating the token, the Azure Function retrieves a new access token to consume Microsoft Graph on behalf of the current user. To do so, the Azure Function relies on the On-Behalf-Of flow, which is described <a href="https://learn.microsoft.com/entra/identity-platform/v2-oauth2-on-behalf-of-flow">here</a>.</p>
<h4>Microsoft Graph Integration</h4>
<p>In the companion sample for this article, the user&#8217;s settings are stored in a file with name <code>settings.json</code> under the <strong>AppRoot</strong> special folder. Here follows an excerpt of the implementation of the service class used to access the special folder and the settings file.</p>
<pre><code class="language-typescript">// Helper: Get approot folder id
async function getAppRootFolderId(graphToken: string) {
  const fetch = (await import("node-fetch")).default;
  const res = await fetch("https://graph.microsoft.com/v1.0/me/drive/special/approot", {
    headers: { Authorization: `Bearer ${graphToken}` }
  });
  if (!res.ok) throw new Error("Failed to get approot folder");
  const data = await res.json();
  if (!data || typeof data !== "object" || !('id' in data)) throw new Error("No id property in approot folder response");
  return (data as { id: string }).id;
}

// Helper: Read settings JSON from approot
async function readSettingsFile(graphToken: string, approotId: string) {
  const res = await fetch(`https://graph.microsoft.com/v1.0/me/drive/items/${approotId}:/settings.json:/content`, {
    headers: { Authorization: `Bearer ${graphToken}` }
  });
  if (res.status === 404) return {}; // No file yet
  if (!res.ok) throw new Error("Failed to read settings file");
  return await res.json();
}

// Helper: Write settings JSON to approot
async function writeSettingsFile(graphToken: string, approotId: string, settings: any) {
  const res = await fetch(`https://graph.microsoft.com/v1.0/me/drive/items/${approotId}:/settings.json:/content`, {
    method: "PUT",
    headers: { Authorization: `Bearer ${graphToken}`, "Content-Type": "application/json" },
    body: JSON.stringify(settings)
  });
  if (!res.ok) throw new Error("Failed to write settings file");
}</code></pre>
<h2>API Endpoint Design</h2>
<p>SharePoint Framework can consume the Azure Function via a set of REST API endpoints to list, get, add, update, or delete settings. Behind the scenes, the Azure Function reads and writes the settings leveraging the <code>settings.json</code> file.</p>
<h3>RESTful Interface</h3>
<p>The REST API endpoints in the Azure Function are defined as follows:</p>
<pre><code class="language-typescript">export async function userSettings(request: HttpRequest, context: InvocationContext): Promise {
  try {
    if (request.method === "OPTIONS") {
      // CORS preflight support (skip OAuth)
      return withCorsHeaders({ status: 204 });
    }

    // Require OAuth2 Bearer token
    const authHeader = request.headers.get("authorization");
    if (!authHeader?.startsWith("Bearer ")) {
      return withCorsHeaders({ status: 401, body: "Missing or invalid Authorization header" });
    }
    const userToken = authHeader.replace("Bearer ", "");

    // Validate the token
    if (!await validateToken(userToken)) {
      return withCorsHeaders({ status: 401, body: "Unauthorized - Token missing or not valid" }); // Token is invalid
    }

    // Get OBO token for Graph API
    const graphToken = await getOboToken(userToken);

    // Get approot folder ID
    const approotId = await getAppRootFolderId(graphToken);

    // Read current settings
    let settings = await readSettingsFile(graphToken, approotId);

    // Parse key from URL (for PUT/DELETE)
    const urlParts = request.url.split("/");
    const key = decodeURIComponent(urlParts[urlParts.length - 1] || "");

    if (request.method === "GET") {
      // List all settings
      const response = Object.entries(settings).map(([k, v]) =&gt; ({ key: k, value: v }));
      return withCorsHeaders({ status: 200, jsonBody: response });
    }

    if (request.method === "POST") {
      // Add new setting
      const value = await request.json();
      if (!key || typeof value !== "string") return withCorsHeaders({ status: 400, body: "Missing key or value" });
      if (settings[key]) return withCorsHeaders({ status: 409, body: "Key already exists" });
      settings[key] = value;
      await writeSettingsFile(graphToken, approotId, settings);
      return withCorsHeaders({ status: 201, body: "Setting added" });
    }

    if (request.method === "PUT") {
      // Update setting
      const value = await request.json();
      if (!key || typeof value !== "string") return withCorsHeaders({ status: 400, body: "Missing key or value" });
      if (!settings[key]) return withCorsHeaders({ status: 404, body: "Key not found" });
      settings[key] = value;
      await writeSettingsFile(graphToken, approotId, settings);
      return withCorsHeaders({ status: 200, body: "Setting updated" });
    }

    if (request.method === "DELETE") {
      // Remove setting
      if (!key) return withCorsHeaders({ status: 400, body: "Missing key" });
      if (!settings[key]) return withCorsHeaders({ status: 404, body: "Key not found" });
      delete settings[key];
      await writeSettingsFile(graphToken, approotId, settings);
      return withCorsHeaders({ status: 200, body: "Setting removed" });
    }

    return withCorsHeaders({ status: 405, body: "Method not allowed" });
  } catch (err: any) {
    context.error(err);
    return withCorsHeaders({ status: 500, body: err.message || "Internal server error" });
  }
}</code></pre>
<p>You can clearly see that all the CRUD (Create, Read, Update, Delete) functionalities are offered through the corresponding REST endpoints (POST, GET, PUT, DELETE).</p>
<h2>Conclusion</h2>
<p>This comprehensive approach to user settings management in SharePoint Framework provides a robust, secure, and scalable solution that leverages the full power of the Microsoft 365 ecosystem. By implementing this pattern, developers can create enterprise-ready applications that offer personalized experiences while maintaining the highest security standards.</p>
<p>The solution&#8217;s architecture ensures cross-device synchronization, per-user data isolation, and enterprise scalability, making it an ideal choice for organizations seeking to deliver sophisticated SharePoint Framework solutions.</p>
<p>The post <a href="https://devblogs.microsoft.com/microsoft365dev/mastering-user-settings-in-sharepoint-framework/">Mastering User Settings in SharePoint Framework</a> appeared first on <a href="https://devblogs.microsoft.com/microsoft365dev">Microsoft 365 Developer Blog</a>.</p>
