---
title: "SharePoint Site Creation in Microsoft Graph"
url: "https://devblogs.microsoft.com/microsoft365dev/sharepoint-site-creation-in-microsoft-graph/"
date: "Mon, 24 Nov 2025 11:51:13 +0000"
author: "SharePoint team"
feed_url: "https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/feed/"
---
<p>The SharePoint team is excited to (finally) bring <a href="https://learn.microsoft.com/en-us/graph/api/site-post-sites">Site Collection creation to Graph</a>! Starting in Microsoft Graph beta you can now create new site collections!</p>
<p>But that’s not all! Creating site collections through older APIs required that your application have <em>Sites.FullControl.All</em> – which is a tenant-wide high-privilege scope that grants access to essentially everything. Because that just isn’t a good model for a site provisioning model we’re also introducing a new scope, <em>Sites.Create.All</em> allowing for a low-permission site provisioning flow. Read on to learn how?</p>
<h2>Create A Site</h2>
<p>Creating a site follows the normal pattern of issuing a POST request to the <em>/sites</em> endpoint. An example body is show below:</p>
<pre class="prettyprint language-json"><code class="language-json">{
  "name": "Communication Site Test",
  "webUrl": "https://contoso.sharepoint.com/sites/commsite1",
  "locale": "en-US",
  "shareByEmailEnabled": false,
  "description": "Test Site Description",
  "template": "sitepagepublishing",
  "ownerIdentityToResolve": {
    "email": "ryan@contoso.com"
  }
}</code></pre>
<p>A few notes, be sure to <a href="https://learn.microsoft.com/en-us/graph/api/site-post-sites?view=graph-rest-beta&amp;tabs=http#request-body">check out the docs</a> for all the details:</p>
<ul>
<li>webUrl is the absolute url within your tenant where you want the site created</li>
<li>template supports three options
<ul>
<li>sts – team site</li>
<li>sitepagepublishing – publishing/communication site</li>
</ul>
</li>
<li>ownerIdentityToResolve is required when calling in application-only mode</li>
</ul>
<h2>Use Sites.Create.All to Improve Security</h2>
<p>To create a more secure provisioning experience we are also introducing the <em>Sites.Create.All</em> scope. Designed to be used with <em>Sites.Selected</em>, this scope allows your application, in both delegated and application-only flows to create new site collections but not read any existing site collections to which it does not have explicit permissions.</p>
<p>Once the site collection is created, the <em>Sites.Create.All</em> scope provides no additional access or control – instead the calling application is auto-granted <em>Sites.Selected</em> + <em>FullControl</em> of the new site collection. At this point the application permissions can be managed like any other, including full removal from the site.</p>
<p>Once created the site can be managed and further setup by the creating application through the <em>Sites.Selected</em> permissions. Lists and Libraries can be created, other applications added to the site, and other provisioning actions can be completed.</p>
<p><figure class="wp-caption alignnone" id="attachment_25046"><a href="https://devblogs.microsoft.com/microsoft365dev/wp-content/uploads/sites/73/2025/11/sharepoitn-graph-site-creation.webp"><img alt="SharePoint Site Creation Microsoft Graph" class="size-full wp-image-25046" height="591" src="https://devblogs.microsoft.com/microsoft365dev/wp-content/uploads/sites/73/2025/11/sharepoitn-graph-site-creation.webp" width="600" /></a><figcaption class="wp-caption-text" id="figcaption_attachment_25046">Figure 1: Sequence Diagram showing which scopes apply during a series of provisioning calls.</figcaption></figure></p>
<p>The creating application maintains access, allowing for centralized idempotent provisioning designs. It would also be possible to have multiple provisioning applications for different audiences like HR or Finance where the central app would manage only those sites with custom business logic and controls.</p>
<p>To see this in action, give your application <em>Sites.Create.All</em> and <em>Sites.Selected</em> scopes, and call the API as described above.</p>
<h3>Migrating to Sites.Create.All</h3>
<p>For your applications that create site collections today, you can swap <em>Sites.FullControl.All</em> for <em>Sites.Create.All</em> and <em>Sites.Selected</em>. Moving forward for any new sites your provisioning code should remain mostly unchanged.</p>
<p>For existing sites provisioned before this update, you need to run a script to add the application permissions to the already created sites. This can be done using calls to <a href="https://learn.microsoft.com/en-us/graph/api/site-post-permissions?view=graph-rest-beta&amp;tabs=http#http-request">/permissions</a> for each site.</p>
<h2>Call To Action</h2>
<p>These are two long required features, and we’re excited to bring them to you! Now is a great time to review your provisioning applications to see if migrating to this lower-permission model is a good fit. <a href="https://learn.microsoft.com/en-us/graph/permissions-selected-overview">Review the Sites.Selected model</a>, and for ISVs and vendors creating provisioning solutions – we hope this reduces the friction where <em>Sites.FullControl.All</em> was previously required. Let us know your input and feedback on the comments.</p>
<p>The post <a href="https://devblogs.microsoft.com/microsoft365dev/sharepoint-site-creation-in-microsoft-graph/">SharePoint Site Creation in Microsoft Graph</a> appeared first on <a href="https://devblogs.microsoft.com/microsoft365dev">Microsoft 365 Developer Blog</a>.</p>
