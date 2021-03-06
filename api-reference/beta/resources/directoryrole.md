---
title: "directoryRole resource type"
description: "Represents an Azure AD directory role. Azure AD directory roles are also known as *administrator roles*. For more information about directory (administrator) roles, see Assigning administrator roles in Azure AD. With the Microsoft Graph, you can assign users to directory roles to grant them the permissions of the target role. To read a directory role or update its members, it must first be activated in the tenant. Only the Company Administrators directory role is activated by default. To activate other available directory roles, you send a POST request with the ID of the directoryRoleTemplate on which the directory role is based. Inherits from directoryObject."
localization_priority: Normal
---

# directoryRole resource type

> **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

Represents an Azure AD directory role. Azure AD directory roles are also known as *administrator roles*. For more information about directory (administrator) roles, see [Assigning administrator roles in Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/). With the Microsoft Graph, you can assign users to directory roles to grant them the permissions of the target role. To read a directory role or update its members, it must first be activated in the tenant. Only the Company Administrators directory role is activated by default. To activate other available directory roles, you send a POST request with the ID of the [directoryRoleTemplate](directoryroletemplate.md) on which the directory role is based. Inherits from [directoryObject](directoryobject.md).

By default, directory roles are scoped to be tenant-wide.  However, directory roles (currently only the *user account admin* and *helpdesk admin*) may also be scoped to [administrative units](administrativeunit.md).

This resource supports:

- Using [delta query](/graph/delta-query-overview) to track incremental additions, deletions, and updates, by providing a [delta](../api/directoryrole-delta.md) function.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get directoryRole](../api/directoryrole-get.md) | [directoryRole](directoryrole.md) |Read properties and relationships of directoryRole object.|
|[List directoryRoles](../api/directoryrole-list.md) | [directoryRole](directoryrole.md) collection | List the directory roles that are activated in the tenant. |
|[Add member](../api/directoryrole-post-members.md) |[directoryObject](directoryobject.md)| Add a user to the directory role by posting to the members navigation property.|
|[List members](../api/directoryrole-list-members.md) |[directoryObject](directoryobject.md) collection| Get the users that are members of the directory role from the members navigation property.|
|[Remove a member](../api/directoryrole-delete-member.md) |[directoryObject](directoryobject.md)| Remove a user from the directory role.|
|[List scoped-role members](../api/directoryrole-list-members.md) |[scopedRoleMembership](scopedrolemembership.md) collection| List the members of this directory role that are scoped to [administrative units](administrativeunit.md), through the scopedRoleMembership resource collection.|
|[delta](../api/directoryrole-delta.md)|directoryRole collection| Get incremental changes for directory roles. |

## Properties
| Property   | Type |Description|
|:---------------|:--------|:----------|
|description|String|The description for the directory role. Read-only. |
|displayName|String|The display name for the directory role. Read-only. |
|id|String|The unique identifier for the directory role. Inherited from [directoryObject](directoryobject.md). Key, Not nullable, Read-only.|
|roleTemplateId|String| The **id** of the [directoryRoleTemplate](directoryroletemplate.md) that this role is based on. The property must be specified when activating a directory role in a tenant with a POST operation. After the directory role has been activated, the property is read only. |

## Relationships
| Relationship | Type |Description|
|:---------------|:--------|:----------|
|members|[directoryObject](directoryobject.md) collection|Users that are members of this directory role. HTTP Methods: GET, POST, DELETE. Read-only. Nullable.|
|scopedMembers|[scopedRoleMembership](scopedrolemembership.md) collection| Members of this directory role that are scoped to [administrative units](administrativeunit.md). Read-only. Nullable.|

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "memberOf",
    "members",
    "ownedObjects",
    "owners"
  ],
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.directoryRole"
}-->

```json
{
  "description": "string",
  "displayName": "string",
  "id": "string (identifier)",
  "roleTemplateId": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "directoryRole resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
