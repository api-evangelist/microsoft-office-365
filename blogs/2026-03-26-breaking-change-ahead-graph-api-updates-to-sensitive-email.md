---
title: "Breaking Change Ahead: Graph API Updates to Sensitive Email Properties"
url: "https://devblogs.microsoft.com/microsoft365dev/graph-api-updates-to-sensitive-email-properties/"
date: "Thu, 26 Mar 2026 18:25:52 +0000"
author: "Thomas Mechelke"
feed_url: "https://developer.microsoft.com/en-us/graph/blogs/feed/"
---
On 12/31/2026, we will begin restricting updates to sensitive properties on non-draft email messages (including subject, body, and recipients). Apps will need Mail-Advanced.ReadWrite (or .All / .Shared) with admin consent to continue modifying these fields. Review your current usage and update permissions now to avoid unexpected failures.
