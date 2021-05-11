---
title: "Create serviceAnnouncementBase"
description: "Create a new serviceAnnouncementBase object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# Create serviceAnnouncementBase
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|**TODO: Provide applicable permissions.**|
|Delegated (personal Microsoft account)|**TODO: Provide applicable permissions.**|
|Application|**TODO: Provide applicable permissions.**|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST ** Collection URI for m365ServiceHealth.readServices.commercialWebService.models.serviceAnnouncementBase not found
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object.

The following table shows the properties that are required when you create the [serviceAnnouncementBase](../resources/serviceannouncementbase.md).

|Property|Type|Description|
|:---|:---|:---|
|startDateTime|DateTimeOffset|**TODO: Add Description**|
|endDateTime|DateTimeOffset|**TODO: Add Description**|
|lastModifiedDateTime|DateTimeOffset|**TODO: Add Description**|
|title|String|**TODO: Add Description**|
|details|[keyValuePair](../resources/keyvaluepair.md) collection|**TODO: Add Description**|
|id|String|**TODO: Add Description**|



## Response

If successful, this method returns a `201 Created` response code and a [serviceAnnouncementBase](../resources/serviceannouncementbase.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "create_serviceannouncementbase_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta** Collection URI for m365ServiceHealth.readServices.commercialWebService.models.serviceAnnouncementBase not found
Content-Type: application/json
Content-length: 301

{
  "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceAnnouncementBase",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "title": "String",
  "details": [
    {
      "@odata.type": "microsoft.graph.keyValuePair"
    }
  ]
}
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "m365ServiceHealth.readServices.commercialWebService.models.serviceAnnouncementBase"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceAnnouncementBase",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)",
  "title": "String",
  "details": [
    {
      "@odata.type": "microsoft.graph.keyValuePair"
    }
  ],
  "id": "28614261-4261-2861-6142-612861426128"
}
```

