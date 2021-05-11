---
title: "serviceAnnouncementBase resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: resourcePageType
---

# serviceAnnouncementBase resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List serviceAnnouncementBases](../api/serviceannouncementbase-list.md)|[serviceAnnouncementBase](../resources/serviceannouncementbase.md) collection|Get a list of the [serviceAnnouncementBase](../resources/serviceannouncementbase.md) objects and their properties.|
|[Create serviceAnnouncementBase](../api/serviceannouncementbase-create.md)|[serviceAnnouncementBase](../resources/serviceannouncementbase.md)|Create a new [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.|
|[Get serviceAnnouncementBase](../api/serviceannouncementbase-get.md)|[serviceAnnouncementBase](../resources/serviceannouncementbase.md)|Read the properties and relationships of a [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.|
|[Update serviceAnnouncementBase](../api/serviceannouncementbase-update.md)|[serviceAnnouncementBase](../resources/serviceannouncementbase.md)|Update the properties of a [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.|
|[Delete serviceAnnouncementBase](../api/serviceannouncementbase-delete.md)|None|Deletes a [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|details|[keyValuePair](../resources/keyvaluepair.md) collection|**TODO: Add Description**|
|endDateTime|DateTimeOffset|**TODO: Add Description**|
|id|String|**TODO: Add Description**|
|lastModifiedDateTime|DateTimeOffset|**TODO: Add Description**|
|startDateTime|DateTimeOffset|**TODO: Add Description**|
|title|String|**TODO: Add Description**|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.serviceAnnouncementBase",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.serviceAnnouncementBase",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)",
  "title": "String",
  "details": [
    {
      "@odata.type": "microsoft.graph.keyValuePair"
    }
  ],
  "id": "String (identifier)"
}
```

