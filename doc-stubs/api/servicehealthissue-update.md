---
title: "Update serviceHealthIssue"
description: "Update the properties of a serviceHealthIssue object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# Update serviceHealthIssue
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [serviceHealthIssue](../resources/servicehealthissue.md) object.

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
PATCH /serviceAnnouncement/issues/{serviceHealthIssueId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [serviceHealthIssue](../resources/servicehealthissue.md) object.

The following table shows the properties that are required when you update the [serviceHealthIssue](../resources/servicehealthissue.md).

|Property|Type|Description|
|:---|:---|:---|
|startDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|endDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|lastModifiedDateTime|DateTimeOffset|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|title|String|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|details|[keyValuePair](../resources/keyvaluepair.md) collection|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|id|String|**TODO: Add Description** Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md)|
|impactDescription|String|**TODO: Add Description**|
|classification|serviceHealthClassificationType|**TODO: Add Description**. Possible values are: `Advisory`, `Incident`, `unknownFutureValue`.|
|origin|serviceHealthOrigin|**TODO: Add Description**. Possible values are: `Microsoft`, `ThirdParty`, `Customer`, `unknownFutureValue`.|
|posts|[serviceHealthIssuePost](../resources/servicehealthissuepost.md) collection|**TODO: Add Description**|
|status|serviceHealthStatus|**TODO: Add Description**. Possible values are: `ServiceOperational`, `Investigating`, `RestoringService`, `VerifyingService`, `ServiceRestored`, `PostIncidentReviewPublished`, `ServiceDegradation`, `ServiceInterruption`, `ExtendedRecovery`, `FalsePositive`, `InvestigationSuspended`, `Resolved`, `MitigatedExternal`, `Mitigated`, `ResolvedExternal`, `Confirmed`, `Reported`, `UnknownFutureValue`.|
|service|String|**TODO: Add Description**|
|feature|String|**TODO: Add Description**|
|featureGroup|String|**TODO: Add Description**|
|isResolved|Boolean|**TODO: Add Description**|
|highImpact|Boolean|**TODO: Add Description**|



## Response

If successful, this method returns a `200 OK` response code and an updated [serviceHealthIssue](../resources/servicehealthissue.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "update_servicehealthissue"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/serviceAnnouncement/issues/{serviceHealthIssueId}
Content-Type: application/json
Content-length: 594

{
  "@odata.type": "#microsoft.graph.serviceHealthIssue",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "title": "String",
  "details": [
    {
      "@odata.type": "microsoft.graph.keyValuePair"
    }
  ],
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
```


### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.serviceHealthIssue",
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
```

