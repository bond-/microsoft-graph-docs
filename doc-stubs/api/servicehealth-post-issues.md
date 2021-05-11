---
title: "Create serviceHealthIssue"
description: "Create a new serviceHealthIssue object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# Create serviceHealthIssue
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new serviceHealthIssue object.

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
POST /serviceAnnouncement/healthOverviews/{serviceHealthId}/issues
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [serviceHealthIssue](../resources/servicehealthissue.md) object.

The following table shows the properties that are required when you create the [serviceHealthIssue](../resources/servicehealthissue.md).

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

If successful, this method returns a `201 Created` response code and a [serviceHealthIssue](../resources/servicehealthissue.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "create_servicehealthissue_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/serviceAnnouncement/healthOverviews/{serviceHealthId}/issues
Content-Type: application/json
Content-length: 637

{
  "@odata.type": "#m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue",
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
  "truncated": true,
  "@odata.type": "m365ServiceHealth.readServices.commercialWebService.models.serviceHealthIssue"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

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
```

