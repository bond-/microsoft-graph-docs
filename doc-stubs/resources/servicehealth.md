---
title: "serviceHealth resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: resourcePageType
---

# serviceHealth resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List serviceHealths](../api/servicehealth-list.md)|[serviceHealth](../resources/servicehealth.md) collection|Get a list of the [serviceHealth](../resources/servicehealth.md) objects and their properties.|
|[Create serviceHealth](../api/servicehealth-create.md)|[serviceHealth](../resources/servicehealth.md)|Create a new [serviceHealth](../resources/servicehealth.md) object.|
|[Get serviceHealth](../api/servicehealth-get.md)|[serviceHealth](../resources/servicehealth.md)|Read the properties and relationships of a [serviceHealth](../resources/servicehealth.md) object.|
|[Update serviceHealth](../api/servicehealth-update.md)|[serviceHealth](../resources/servicehealth.md)|Update the properties of a [serviceHealth](../resources/servicehealth.md) object.|
|[Delete serviceHealth](../api/servicehealth-delete.md)|None|Deletes a [serviceHealth](../resources/servicehealth.md) object.|
|[List issues](../api/servicehealth-list-issues.md)|[serviceHealthIssue](../resources/servicehealthissue.md) collection|Get the serviceHealthIssue resources from the issues navigation property.|
|[Create serviceHealthIssue](../api/servicehealth-post-issues.md)|[serviceHealthIssue](../resources/servicehealthissue.md)|Create a new serviceHealthIssue object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|**TODO: Add Description**|
|service|String|**TODO: Add Description**|
|status|serviceHealthStatus|**TODO: Add Description**. Possible values are: `ServiceOperational`, `Investigating`, `RestoringService`, `VerifyingService`, `ServiceRestored`, `PostIncidentReviewPublished`, `ServiceDegradation`, `ServiceInterruption`, `ExtendedRecovery`, `FalsePositive`, `InvestigationSuspended`, `Resolved`, `MitigatedExternal`, `Mitigated`, `ResolvedExternal`, `Confirmed`, `Reported`, `UnknownFutureValue`.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|issues|[serviceHealthIssue](../resources/servicehealthissue.md) collection|**TODO: Add Description**|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.serviceHealth",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.serviceHealth",
  "service": "String",
  "status": "String",
  "id": "String (identifier)"
}
```

