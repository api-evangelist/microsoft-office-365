---
title: "Change to data visibility for Microsoft Graph callRecords APIs in GCC High and DoD"
url: "https://devblogs.microsoft.com/microsoft365dev/change-to-data-visibility-for-microsoft-graph-callrecords-apis-in-gcc-high-and-dod/"
date: "Mon, 08 Sep 2025 18:35:58 +0000"
author: "Matthew McGrath"
feed_url: "https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/feed/"
---
<p><span>As a continuation of changes </span><a href="https://devblogs.microsoft.com/microsoft365dev/recent-changes-to-data-visibility-for-microsoft-graph-callrecords-apis/"><span>previously announced</span></a><span> for global customers, we will be making changes to how Microsoft handles Microsoft Teams call data in GCC High and DoD environments that we expose via the Microsoft Graph <strong>callRecords</strong> APIs (beta and v1.0). </span><span> </span></p>
<p><span>For organizations that participate in a federated call or meeting but did not initiate it (non-owning organizations), they will now only be able to see usage and diagnostic data for users within their own organization. For consistency, this change has been applied to all federated calls and meetings – not only those that cross a regional boundary. The schema of the API remains unchanged so most application code will not be affected. </span><span> </span></p>
<p><span>While we understand that this change might impact some applications that depend on our API, we believe this change is important to meet our commitments to reduce cross-region data flows while still enabling customers to take advantage of diagnostic data to troubleshoot poor quality calls and understand their organization’s Microsoft Teams usage. </span><span> </span></p>
<p><span>This change will go into effect in early October 2025.</span><span> </span></p>
<p><span>Happy coding! </span><span> </span></p>
<p>The post <a href="https://devblogs.microsoft.com/microsoft365dev/change-to-data-visibility-for-microsoft-graph-callrecords-apis-in-gcc-high-and-dod/">Change to data visibility for Microsoft Graph callRecords APIs in GCC High and DoD</a> appeared first on <a href="https://devblogs.microsoft.com/microsoft365dev">Microsoft 365 Developer Blog</a>.</p>
