---
title: "Introducing the Microsoft Graph User Configuration API (preview)"
url: "https://devblogs.microsoft.com/microsoft365dev/introducing-the-microsoft-graph-user-configuration-api-preview/"
date: "Wed, 28 Jan 2026 18:59:42 +0000"
author: "Cameron Parker"
feed_url: "https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/feed/"
---
<p><span>We’re excited to announce the public preview of the User Configuration API in the Microsoft Graph beta endpoint. The User Configuration API is a new set of endpoints that you can use to create, read, update, and delete user configuration objects in Exchange Online mail folders.  User configuration objects—also known as folder associated items (FAIs)—are items associated with a specific mail folder, and each configuration object in a folder must have a unique key. </span><span> </span></p>
<p><span>Many solutions need a reliable way to store and retrieve per-folder configuration data alongside mailbox content—whether that’s application state, settings, or other metadata scoped to a folder.  The <strong>userConfiguration</strong> resource supports multiple payload styles so you can store what best fits your scenario:</span><span> </span></p>
<ul>
<li><span><strong>binaryData</strong>: arbitrary binary data</span><span> </span></li>
</ul>
<ul>
<li><span><strong>xmlData</strong>: serialized XML</span><span> </span></li>
</ul>
<ul>
<li><span><strong>structuredData</strong>: key-value pairs of supported data types</span><span> </span></li>
</ul>
<h2>API capabilities</h2>
<p><span>The beta release includes full CRUD support for <strong>userConfiguration</strong> objects:</span><span> </span></p>
<ul>
<li>Create<span> a new <strong>userConfiguration</strong></span><span> </span></li>
</ul>
<ul>
<li>Get<span> an existing <strong>userConfiguration</strong></span><span> </span></li>
</ul>
<ul>
<li>Update<span> an existing <strong>userConfiguration</strong></span><span> </span></li>
</ul>
<ul>
<li>Delete<span> a <strong>userConfiguration</strong></span><span> </span></li>
</ul>
<p><span>For example, you can read a configuration from either the signed-in user (/me) or a specific user (/users/{id}), scoped to a mail folder:</span><span> </span></p>
<ul>
<li class="prettyprint language-html"><code class="language-html">GET /me/mailFolders/{mailFolderId}/userConfigurations/{userConfigurationId}</code></li>
</ul>
<ul>
<li class="prettyprint language-html"><code class="language-html">GET /users/{usersId}/mailFolders/{mailFolderId}/userConfigurations/{userConfigurationId}</code></li>
</ul>
<h2><b><span>Permissions (least privileged)</span></b><span> </span></h2>
<p><span>The API uses dedicated permissions for mailbox configuration items:</span><span> </span></p>
<ul>
<li>Get<span> supports <code>MailboxConfigItem.Read</code> (least privileged) and <code>MailboxConfigItem.ReadWrite</code> (higher privileged)</span><span> </span></li>
</ul>
<ul>
<li>Create<span> requires <code>MailboxConfigItem.ReadWrite</code></span></li>
</ul>
<ul>
<li>Update<span> requires <code>MailboxConfigItem.ReadWrite</code></span><code><span> </span></code></li>
</ul>
<ul>
<li>Delete <span>requires <code>MailboxConfigItem.ReadWrite</code></span><span> </span></li>
</ul>
<p><span>As always, choose the </span><b><span>l</span></b>east privileged permissions<span> your application needs.</span><span> </span></p>
<h2><b><span>Get started</span></b><span> </span></h2>
<p><span>The easiest way to begin is to explore the API surface and try calls interactively.</span></p>
<p><span>Review the resource and method docs:</span><span> </span></p>
<ul>
<li><a href="https://learn.microsoft.com/en-us/graph/api/resources/userconfiguration?view=graph-rest-beta"><span>userConfiguration resource type</span></a><span> </span></li>
</ul>
<ul>
<li><a href="https://learn.microsoft.com/en-us/graph/api/mailsearchfolder-post-userconfigurations?view=graph-rest-beta"><span>Create userConfiguration</span></a></li>
</ul>
<ul>
<li><a href="https://learn.microsoft.com/en-us/graph/api/userconfiguration-get?view=graph-rest-beta"><span>Get userConfiguration</span></a></li>
</ul>
<ul>
<li><a href="https://learn.microsoft.com/en-us/graph/api/userconfiguration-update?view=graph-rest-beta"><span>Update userConfiguration</span></a></li>
</ul>
<ul>
<li><a href="https://learn.microsoft.com/en-us/graph/api/userconfiguration-delete?view=graph-rest-beta"><span>Delete userConfiguration</span></a></li>
</ul>
<p><span>Use Graph Explorer to test requests quickly:</span><span> </span></p>
<ul>
<li><a href="https://developer.microsoft.com/en-us/graph/graph-explorer"><span>Graph Explorer | Try Microsoft Graph APIs</span></a><span> </span></li>
</ul>
<h2><b><span>We’d love your feedback</span></b><span> </span></h2>
<p><span>As you explore the User Configuration API in beta, we want to hear what’s working well and where we can improve—especially around usability, gaps, and real-world scenarios.</span><span> </span></p>
<p><span>Send feedback to: </span><a href="mailto:exouserconfigurationapifeedback@microsoft.com"><span>exouserconfigurationapifeedback@microsoft.com</span></a><span> </span></p>
<p>The post <a href="https://devblogs.microsoft.com/microsoft365dev/introducing-the-microsoft-graph-user-configuration-api-preview/">Introducing the Microsoft Graph User Configuration API (preview)</a> appeared first on <a href="https://devblogs.microsoft.com/microsoft365dev">Microsoft 365 Developer Blog</a>.</p>
