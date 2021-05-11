---
title: "List issues"
description: "Get the serviceHealthIssue resources from the issues navigation property."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# List issues
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the serviceHealthIssue resources from the issues navigation property.

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
GET /serviceAnnouncement/issues
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

If successful, this method returns a `200 OK` response code and a collection of [serviceHealthIssue](../resources/servicehealthissue.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_servicehealthissue"
}
-->
``` http
GET https://graph.microsoft.com/beta/serviceAnnouncement/issues
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue",
      "startDateTime": "String (timestamp)",
      "endDateTime": "String (timestamp)",
      "lastModifiedDateTime": "String (timestamp)",
      "title": "String",
      "details": [
        {
          "@odata.type": "microsoft.graph.keyValuePair"
        }
      ],
      "id": "c5c63ad1-3ad1-c5c6-d13a-c6c5d13ac6c5",
      "impactDescription": "String",
      "classification": "String",
      "origin": "String",
      "posts": [
        {
          "@odata.type": "microsoft.graph.serviceHealthIssuePost"
        }
      ],
      "status": "String",
      "service": "String",
      "feature": "String",
      "featureGroup": "String",
      "isResolved": "Boolean",
      "highImpact": "Boolean"
    }
  ]
}
```

