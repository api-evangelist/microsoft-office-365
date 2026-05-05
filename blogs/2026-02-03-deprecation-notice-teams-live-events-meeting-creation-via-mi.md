---
title: "Deprecation notice: Teams Live Events meeting creation via Microsoft Graph"
url: "https://devblogs.microsoft.com/microsoft365dev/deprecation-notice-teams-live-events-meeting-creation-via-microsoft-graph/"
date: "Tue, 03 Feb 2026 16:55:49 +0000"
author: "Microsoft Graph team"
feed_url: "https://devblogs.microsoft.com/microsoft365dev/category/microsoft-graph/feed/"
---
<p><!--ScriptorStartFragment--></p>
<div class="scriptor-paragraph">We’re announcing an important change for developers using Microsoft Graph APIs to create Teams Live Events. Starting March 31, 2026, the beta endpoint will no longer support the <code class="language-PlainText">isBroadcast</code> property of the <code class="language-PlainText">onlineMeeting</code> resource. This property has historically been used to create Teams Live Events meetings. The same change will apply to the v1.0 endpoint on June 30, 2026.</div>
<h2>What’s changing?</h2>
<ul class="">
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544420">The <code class="language-PlainText">isBroadcast</code> property is deprecated and will be removed from the <code class="language-PlainText">onlineMeeting</code> resource.</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544420">Creating Teams Live Events meetings by using this property will no longer be supported.</li>
</ul>
<h2>What should you do instead?</h2>
<div class="scriptor-paragraph">Teams Live Events are being retired in favor of Virtual Events, which provide richer functionality and flexibility for large-scale events. To transition, you can use:</div>
<ul class="">
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544421">Webinars (<code class="language-PlainText">virtualEventWebinar</code>)</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544421">Town halls (<code class="language-PlainText">virtualEventTownhall</code>)</li>
</ul>
<div class="scriptor-paragraph">These APIs offer advanced capabilities such as:</div>
<ul class="">
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544422">Registration management</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544422">Session and presenter configuration</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544422">Attendance reporting</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544422">Integration with Teams client for a seamless experience</li>
</ul>
<div class="scriptor-paragraph">To learn more about the Virtual Event APIs and how to implement them in your apps, see <a href="https://learn.microsoft.com/en-us/graph/cloud-communications-virtual-events-overview"><span>Teams meeting type and Microsoft Graph APIs.</span></a></div>
<h2>Timeline</h2>
<ul class="">
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544423">March 31, 2026: Removal in beta.</li>
<li class="scriptor-listItemlist!list-eadcfa23-acb9-4d30-9838-03154a0544423">June 30, 2026: Removal in v1.0.</li>
</ul>
<h2>Why this matters</h2>
<div class="scriptor-paragraph">Virtual Event APIs are designed to support modern collaboration scenarios, offering scalability and features that go beyond what Teams Live Events provided. Migrating now ensures your apps remain compatible and take advantage of new capabilities.</div>
<p><!--ScriptorEndFragment--></p>
<p>The post <a href="https://devblogs.microsoft.com/microsoft365dev/deprecation-notice-teams-live-events-meeting-creation-via-microsoft-graph/">Deprecation notice: Teams Live Events meeting creation via Microsoft Graph</a> appeared first on <a href="https://devblogs.microsoft.com/microsoft365dev">Microsoft 365 Developer Blog</a>.</p>
