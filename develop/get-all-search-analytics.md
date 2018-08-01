---
title: Get all search analytics information
description: How to get all the search analytics information. 
author: Xansky
ms.author: mhopkins   
ms.assetid: CCF9D929-EE5F-4141-9884-ECA559A5171B
robots: noindex,nofollow   
ms.date: 06/27/2018
ms.topic: article
ms.prod: partner-center
ms.technology: partner-center-sdk
---

# Get all search analytics information

>[!IMPORTANT]   
>This information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here. 

**Applies To**

-   Partner Center
-   Partner Center operated by 21Vianet
-   Partner Center for Microsoft Cloud Germany
-   Partner Center for Microsoft Cloud for US Government


How to get all the search analytics information for your customers. 

## <span id="Prerequisites"></span><span id="prerequisites"></span><span id="PREREQUISITES"></span>Prerequisites


-   Credentials as described in [Partner Center authentication](partner-center-authentication.md). This scenario supports authentication with User credentials only. 

## <span id="Request"></span><span id="request"></span><span id="REQUEST"></span>REST Request


**Request syntax**

| Method  | Request URI |
|---------|-------------|
| **GET** | [*\{baseURL\}*](partner-center-rest-urls.md)/partner/v1/analytics/search |

 

**URI parameters**

| Parameter | Type | Description |
|-----------|------|-------------|
| filter | string | Returns data matching the filter condition. </br> **Example:**</br> `.../search?filter=field eq 'value'`|
| groupby | string | Supports both terms and dates. Short circuit logic to limit the number of buckets. </br> **Example:**</br> `.../search?groupby=termField1,dateField1,termField2` |
| aggregationLevel | string |	The *aggregationLevel* parameter requires a *groupby*. The *aggregationLevel* parameter applies to all date fields present in the *groupby*. </br> **Example:**</br>  `.../search?groupby=termField1,dateField1,termField2&aggregationLevel=day` | No |
| top | string | The page limit is 10000. Takes any value less than 10000.  </br> **Example:**</br>  `.../search?top=100` |
| skip | string | Number of rows to skip. </br> **Example:**</br> `.../search?top=100&skip=100` |

  
**Request headers**

-   See [Headers](headers.md) for more information.

**Request body**

None.

**Request example**

```
GET https://api.partnercenter.microsoft.com/partner/v1/analytics/search
Authorization: Bearer <token>
Accept: application/json
Content-Type: application/json
Content-Length: 0
```

## <span id="Response"></span><span id="response"></span><span id="RESPONSE"></span>Response


If successful, the response body contains a collection of [Search](partner-center-analytics-resources.md#search_resource) resources.

**Response success and error codes**

Each response comes with an HTTP status code that indicates success or failure and additional debugging information. Use a network trace tool to read this code, error type, and additional parameters. For the full list, see [Error Codes](error-codes.md).

**Response example**

```
{
  "companyName": "my company",
  "contactButtonClicked": false,
  "keywordCountry": null,
  "detailsViewed": true,
  "keywordIndustryFocus": null,
  "mpnId": 2604568,
  "partnerMarket": "CN",
  "keywordProduct": null,
  "referralSubmitted": false,
  "searchDate": "2018-05-30",
  "keywordSearchText": " my company"
}
```


## <span id="See_Also"></span><span id="see_also"></span><span id="SEE_ALSO"></span>See also
 - [Partner Center Analytics - Resources](partner-center-analytics-resources.md)