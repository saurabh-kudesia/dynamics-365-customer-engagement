---
title: Delete Data Connector Mapping (Hub)
description: Deletes the specified Data Connector Mapping.
keywords: Customer Insights; Hub API; Data Connector Mapping; delete
author: JimDaly
ms.author: jdaly
manager: jdaly
ms.date: 06/06/2017
ms.topic: reference
ms.service: customer-insights 
ms.assetid: 98986c28-da82-42e6-86d4-fcc8f39201b9
---

Delete Data Connector (Hub)
==========================

[!include[pre release disclaimer](../../../includes/cc-beta-prerelease-disclaimer.md)]

Deletes the specified Data [Connector Mapping](../types/connectormapping.md).

## Request 
The request is constructed as follows:

|**HTTP Verb**|**Request URI**|
|-------------|---------------|
|DELETE|`<hub-endpoint>/manage/connectors/<connectorName>/mappings/<mappingName>?api-version=2017-04-26`|

### URI Parameters

|**URI Parameter**|**Required**|**Description**|
| --------------- | ---------- | ------------- |
|subId|Yes|Subscription ID|
|rgName|Yes|Azure region name|
|hubName|Yes|Name of your Customer Insights Hub|
|connectorName|Yes|Name of the data connector that contains the mapping|
|mappingName|Yes|Name of the mapping to delete|
| | | |

## Response  
 The response includes a standard HTTP status code and a set of standard response headers.


### Status Code  
  
-   200 (OK) - Delete succeeded
-   204 (No Content) - Delete succeeded, but the response body is intentionally empty




