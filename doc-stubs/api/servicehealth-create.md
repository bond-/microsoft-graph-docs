---
title: "Create serviceHealth"
description: "Create a new serviceHealth object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# Create serviceHealth
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [serviceHealth](../resources/servicehealth.md) object.

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
POST /serviceAnnouncement/healthOverviews
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [serviceHealth](../resources/servicehealth.md) object.

The following table shows the properties that are required when you create the [serviceHealth](../resources/servicehealth.md).

|Property|Type|Description|
|:---|:---|:---|
|service|String|**TODO: Add Description**|
|status|serviceHealthStatus|**TODO: Add Description**. Possible values are: `ServiceOperational`, `Investigating`, `RestoringService`, `VerifyingService`, `ServiceRestored`, `PostIncidentReviewPublished`, `ServiceDegradation`, `ServiceInterruption`, `ExtendedRecovery`, `FalsePositive`, `InvestigationSuspended`, `Resolved`, `MitigatedExternal`, `Mitigated`, `ResolvedExternal`, `Confirmed`, `Reported`, `UnknownFutureValue`.|
|id|String|**TODO: Add Description**|



## Response

If successful, this method returns a `201 Created` response code and a [serviceHealth](../resources/servicehealth.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "create_servicehealth_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/serviceAnnouncement/healthOverviews
Content-Type: application/json
Content-length: 145

{
  "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceHealth",
  "service": "String",
  "status": "String"
}
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "m365ServiceHealth.readServices.commercialWebService.models.serviceHealth"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceHealth",
  "service": "String",
  "status": "String",
  "id": "aeacd13b-d13b-aeac-3bd1-acae3bd1acae"
}
```

