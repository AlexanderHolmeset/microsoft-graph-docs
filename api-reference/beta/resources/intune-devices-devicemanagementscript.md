---
title: "deviceManagementScript resource type"
description: "Intune will provide customer the ability to run their Powershell scripts on the enrolled windows 10 Azure Active Directory joined devices. The script can be run once or periodically."
author: "tfitzmac"
localization_priority: Normal
---

# deviceManagementScript resource type

> **Important:** APIs under the / beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

> **Note:** Using the Microsoft Graph APIs to configure Intune controls and policies still requires that the Intune service is [correctly licensed](https://go.microsoft.com/fwlink/?linkid=839381) by the customer.

Intune will provide customer the ability to run their Powershell scripts on the enrolled windows 10 Azure Active Directory joined devices. The script can be run once or periodically.
## Methods
|Method|Return Type|Description|
|:---|:---|:---|
|[List deviceManagementScripts](../api/intune-devices-devicemanagementscript-list.md)|[deviceManagementScript](../resources/intune-devices-devicemanagementscript.md) collection|List properties and relationships of the [deviceManagementScript](../resources/intune-devices-devicemanagementscript.md) objects.|
|[Get deviceManagementScript](../api/intune-devices-devicemanagementscript-get.md)|[deviceManagementScript](../resources/intune-devices-devicemanagementscript.md)|Read properties and relationships of the [deviceManagementScript](../resources/intune-devices-devicemanagementscript.md) object.|
|[Create deviceManagementScript](../api/intune-devices-devicemanagementscript-create.md)|[deviceManagementScript](../resources/intune-devices-devicemanagementscript.md)|Create a new [deviceManagementScript](../resources/intune-devices-devicemanagementscript.md) object.|
|[Delete deviceManagementScript](../api/intune-devices-devicemanagementscript-delete.md)|None|Deletes a [deviceManagementScript](../resources/intune-devices-devicemanagementscript.md).|
|[Update deviceManagementScript](../api/intune-devices-devicemanagementscript-update.md)|[deviceManagementScript](../resources/intune-devices-devicemanagementscript.md)|Update the properties of a [deviceManagementScript](../resources/intune-devices-devicemanagementscript.md) object.|
|[assign action](../api/intune-devices-devicemanagementscript-assign.md)|None|Not yet documented|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique Identifier for the device management script.|
|displayName|String|Name of the device management script.|
|description|String|Optional description for the device management script.|
|runSchedule|[runSchedule](../resources/intune-devices-runschedule.md)|The interval for script to run. If not defined the script will run once|
|scriptContent|Binary|The script content.|
|createdDateTime|DateTimeOffset|The date and time the device management script was created.|
|lastModifiedDateTime|DateTimeOffset|The date and time the device management script was last modified.|
|runAsAccount|[runAsAccountType](../resources/intune-shared-runasaccounttype.md)|Indicates the type of execution context the device management script runs in. Possible values are: `system`, `user`.|
|enforceSignatureCheck|Boolean|Indicate whether the script signature needs be checked.|
|fileName|String|Script file name.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|groupAssignments|[deviceManagementScriptGroupAssignment](../resources/intune-devices-devicemanagementscriptgroupassignment.md) collection|The list of group assignments for the device management script.|
|assignments|[deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) collection|The list of group assignments for the device management script.|
|runSummary|[deviceManagementScriptRunSummary](../resources/intune-devices-devicemanagementscriptrunsummary.md)|Run summary for device management script.|
|deviceRunStates|[deviceManagementScriptDeviceState](../resources/intune-devices-devicemanagementscriptdevicestate.md) collection|List of run states for this script across all devices.|
|userRunStates|[deviceManagementScriptUserState](../resources/intune-devices-devicemanagementscriptuserstate.md) collection|List of run states for this script across all users.|

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.deviceManagementScript"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementScript",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "runSchedule": {
    "@odata.type": "microsoft.graph.runSchedule"
  },
  "scriptContent": "binary",
  "createdDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)",
  "runAsAccount": "String",
  "enforceSignatureCheck": true,
  "fileName": "String"
}
```





