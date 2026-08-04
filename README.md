# Microsoft Office 365 (microsoft-office-365)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

A collection of APIs provided by Microsoft Office 365 for productivity, collaboration, and enterprise services.

**APIs.json:** [https://www.microsoft.com/en-us/microsoft-365](https://www.microsoft.com/en-us/microsoft-365)

## Tags

- Cloud
- Collaboration
- Enterprise
- Microsoft
- Productivity

## Timestamps

- **Created:** 2024-01-15
- **Modified:** 2026-05-19

## APIs

### Microsoft Graph API

Unified API endpoint to access data, intelligence, and insights from Microsoft 365, Windows, and Enterprise Mobility + Security.

- **Human URL:** [https://developer.microsoft.com/en-us/graph](https://developer.microsoft.com/en-us/graph)
- **Base URL:** `https://graph.microsoft.com`

#### Tags

- Calendar
- Graph
- Groups
- Mail
- Unified
- Users

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/overview)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/microsoft-graph-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON-LD](json-ld/microsoft-office-365-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
- [Authentication](https://docs.microsoft.com/en-us/graph/auth/)
- [Documentation](https://www.postman.com/microsoftgraph/workspace/microsoft-graph/overview)
- [Terms of Service](https://docs.microsoft.com/en-us/legal/microsoft-apis/terms-of-use)
- [Rate Limits](https://docs.microsoft.com/en-us/graph/throttling)
- [Getting Started](https://learn.microsoft.com/en-us/graph/use-the-api)
- [SDK](https://learn.microsoft.com/en-us/graph/sdks/sdks-overview)
- [Documentation](https://learn.microsoft.com/en-us/graph/change-notifications-overview)
- [Versioning](https://learn.microsoft.com/en-us/graph/versioning-and-support)
- [Console](https://developer.microsoft.com/en-us/graph/graph-explorer)

### Outlook Mail API

Access to Outlook email, including reading, sending, and managing messages.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/mail-api-overview](https://docs.microsoft.com/en-us/graph/api/resources/mail-api-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/messages`

#### Tags

- Email
- Mail
- Messages
- Outlook

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/message)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/mail.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/microsoft-graph-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://learn.microsoft.com/en-us/graph/outlook-change-notifications-overview)

### Outlook Calendar API

Access to Outlook calendar events, scheduling, and meeting management.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/calendar](https://docs.microsoft.com/en-us/graph/api/resources/calendar)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/calendar`

#### Tags

- Calendar
- Events
- Meetings
- Scheduling

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/event)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/calendar.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/microsoft-graph-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Outlook Contacts API

Access to Outlook personal contacts for managing contact information, creating contact folders, and organizing people data.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/outlook-contacts-concept-overview](https://learn.microsoft.com/en-us/graph/outlook-contacts-concept-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/contacts`

#### Tags

- Address-Book
- Contacts
- Outlook
- People

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/contact?view=graph-rest-1.0)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OneDrive API

Access to OneDrive file storage, sharing, and collaboration features.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/onedrive](https://docs.microsoft.com/en-us/graph/api/resources/onedrive)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/drive`

#### Tags

- Files
- Onedrive
- Sharing
- Storage

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/driveitem)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/files.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Getting Started](https://learn.microsoft.com/en-us/onedrive/developer/rest-api/?view=odsp-graph-online)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SharePoint API

Access to SharePoint sites, lists, and document libraries.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/sharepoint](https://docs.microsoft.com/en-us/graph/api/resources/sharepoint)
- **Base URL:** `https://graph.microsoft.com/v1.0/sites`

#### Tags

- Collaboration
- Lists
- Sharepoint
- Sites

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/site)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/sites.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://learn.microsoft.com/en-us/sharepoint/dev/apis/sharepoint-rest-graph)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Teams API

Access to Microsoft Teams channels, messages, and collaboration features.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/teams-api-overview](https://docs.microsoft.com/en-us/graph/api/resources/teams-api-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/teams`

#### Tags

- Channels
- Chat
- Collaboration
- Teams

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/team)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/teams.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Office 365 Users API

Manage Office 365 users, profiles, and organizational information.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/user](https://docs.microsoft.com/en-us/graph/api/resources/user)
- **Base URL:** `https://graph.microsoft.com/v1.0/users`

#### Tags

- Directory
- Identity
- Profiles
- Users

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/user)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/users.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/microsoft-office-365-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Planner API

Access to Microsoft Planner tasks, plans, and project management features.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/api/resources/planner-overview](https://docs.microsoft.com/en-us/graph/api/resources/planner-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/planner`

#### Tags

- Planner
- Planning
- Projects
- Tasks

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/resources/planner-overview)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/microsoft-graph-openapi/master/openapi/v1.0/planner.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OneNote API

Access to OneNote notebooks, sections, and pages for creating and managing notes and structured content.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/integrate-with-onenote](https://learn.microsoft.com/en-us/graph/integrate-with-onenote)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/onenote`

#### Tags

- Notebooks
- Notes
- Onenote
- Pages
- Sections

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/onenote-api-overview?view=graph-rest-1.0)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Excel Workbooks and Charts API

Read and modify Excel workbooks stored in OneDrive and SharePoint, including managing worksheets, tables, charts, ranges, and sessions.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/excel-concept-overview](https://learn.microsoft.com/en-us/graph/excel-concept-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/drive/items/{id}/workbook`

#### Tags

- Charts
- Excel
- Spreadsheets
- Tables
- Workbooks

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/excel?view=graph-rest-1.0)
- [Best Practices](https://learn.microsoft.com/en-us/graph/workbook-best-practice)
- [Documentation](https://learn.microsoft.com/en-us/graph/excel-manage-sessions)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft To Do API

Manage tasks and task lists across To Do clients, Outlook, and Teams for personal task management and day planning.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/todo-concept-overview](https://learn.microsoft.com/en-us/graph/todo-concept-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/me/todo`

#### Tags

- Productivity
- Task-Lists
- Tasks
- Todo

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/todo-concept-overview)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Bookings API

Manage customer bookings, appointment scheduling, business services, and staff information for enterprise and small business owners.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/booking-concept-overview](https://learn.microsoft.com/en-us/graph/booking-concept-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/solutions/bookingBusinesses`

#### Tags

- Appointments
- Bookings
- Business
- Scheduling

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/booking-api-overview?view=graph-rest-1.0)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Office 365 Groups API

Manage Microsoft 365 groups, group membership, conversations, and group-related resources for collaboration.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/api/resources/groups-overview?view=graph-rest-1.0](https://learn.microsoft.com/en-us/graph/api/resources/groups-overview?view=graph-rest-1.0)
- **Base URL:** `https://graph.microsoft.com/v1.0/groups`

#### Tags

- Collaboration
- Groups
- Membership
- Teams

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/group?view=graph-rest-1.0)
- [OpenAPI](openapi/microsoft-graph-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Graph Security API

Connect security products, services, and partners to streamline security operations and improve threat protection, detection, and response.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/security-concept-overview](https://learn.microsoft.com/en-us/graph/security-concept-overview)
- **Base URL:** `https://graph.microsoft.com/v1.0/security`

#### Tags

- Alerts
- Compliance
- Security
- Threats

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/security-api-overview?view=graph-rest-1.0)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Graph Communications API

Create and join online meetings, manage call records, and enable cloud communications capabilities for applications.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/cloud-communications-online-meetings](https://learn.microsoft.com/en-us/graph/cloud-communications-online-meetings)
- **Base URL:** `https://graph.microsoft.com/v1.0/communications`

#### Tags

- Calls
- Communications
- Meetings
- Online-Meetings

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/cloud-communications-online-meetings)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Office Add-ins Platform

Platform for building solutions that extend Office applications including Excel, Outlook, Word, PowerPoint, and OneNote using web technologies and the Office JavaScript API.

- **Human URL:** [https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins)

#### Tags

- Add-Ins
- Excel
- Extensions
- Office-Js
- Outlook
- Powerpoint
- Word

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/office/dev/add-ins/)
- [API Reference](https://learn.microsoft.com/en-us/office/dev/add-ins/reference/javascript-api-for-office)
- [Getting Started](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/learning-path-beginner)
- [Documentation](https://learn.microsoft.com/en-us/office/dev/add-ins/develop/develop-overview)
- [Postman Collection](collections/microsoft-graph-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [LinkedIn](https://www.linkedin.com/showcase/microsoft-365)
- [Developer Portal](https://developer.microsoft.com/en-us/microsoft-365)
- [Status Page](https://status.office365.com/)
- [Support](https://developer.microsoft.com/en-us/graph/support)
- [Blog](https://developer.microsoft.com/en-us/graph/blogs/)
- [GitHub Organization](https://github.com/microsoftgraph)
- [Privacy Policy](https://privacy.microsoft.com/en-us/privacystatement)
- [Console](https://developer.microsoft.com/en-us/graph/graph-explorer)
- [SDK](https://learn.microsoft.com/en-us/graph/sdks/sdks-overview)
- [Changelog](https://developer.microsoft.com/en-us/graph/changelog)
- [Release Notes](https://learn.microsoft.com/en-us/graph/whats-new-overview)
- [Authentication](https://learn.microsoft.com/en-us/graph/auth/)
- [Terms of Service](https://docs.microsoft.com/en-us/legal/microsoft-apis/terms-of-use)
- [Rate Limits](https://learn.microsoft.com/en-us/graph/throttling)
- [Documentation](https://learn.microsoft.com/en-us/graph/change-notifications-delivery-webhooks)
- [Quickstart](https://developer.microsoft.com/en-us/graph/quick-start)
- [API Reference](https://learn.microsoft.com/en-us/graph/api/overview?view=graph-rest-1.0)
- [Compliance](https://learn.microsoft.com/en-us/graph/compliance-concept-overview)
- [Spectral Rules](rules/microsoft-office-365-spectral-rules.yml)
- [Features](https://developer.microsoft.com/en-us/graph)
- [Use Cases](https://developer.microsoft.com/en-us/graph)
- [Integrations](https://developer.microsoft.com/en-us/graph)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
**URL:** https://apievangelist.com
