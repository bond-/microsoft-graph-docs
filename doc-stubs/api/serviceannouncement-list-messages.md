---
title: "List messages"
description: "Get the serviceUpdateMessage resources from the messages navigation property."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# List messages
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the serviceUpdateMessage resources from the messages navigation property.

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
GET /serviceAnnouncement/messages
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [serviceUpdateMessage](../resources/serviceupdatemessage.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_serviceupdatemessage"
}
-->
``` http
GET https://graph.microsoft.com/beta/serviceAnnouncement/messages
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(m365ServiceHealth.readServices.commercialWebService.models.serviceUpdateMessage)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceUpdateMessage",
      "startDateTime": "String (timestamp)",
      "endDateTime": "String (timestamp)",
      "lastModifiedDateTime": "String (timestamp)",
      "title": "String",
      "details": [
        {
          "@odata.type": "microsoft.graph.keyValuePair"
        }
      ],
      "id": "a83ec490-c490-a83e-90c4-3ea890c43ea8",
      "body": {
        "@odata.type": "microsoft.graph.itemBody"
      },
      "category": "String",
      "severity": "String",
      "tags": [
        "String"
      ],
      "isMajorChange": "Boolean",
      "actionRequiredByDateTime": "String (timestamp)",
      "services": [
        "String"
      ],
      "viewPoint": {
        "@odata.type": "microsoft.graph.serviceUpdateMessageViewpoint"
      },
      "expiryDateTime": "String (timestamp)"
    }
  ]
}
```

