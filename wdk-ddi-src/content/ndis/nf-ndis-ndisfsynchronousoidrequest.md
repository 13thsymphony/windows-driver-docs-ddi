---
UID: NF:ndis.NdisFSynchronousOidRequest
title: NdisFSynchronousOidRequest function
author: windows-driver-content
description: This function is reserved.
old-location: netvista\ndisfsynchronousoidrequest.htm
old-project: netvista
ms.assetid: 01B625EB-AB6D-496F-95F2-22845460324A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFSynchronousOidRequest function [Network Drivers Starting with Windows Vista], netvista.ndisfsynchronousoidrequest, NdisFSynchronousOidRequest, ndis/NdisFSynchronousOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFSynchronousOidRequest
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFSynchronousOidRequest function
<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div><div> </div>This function is reserved.

## Syntax

````
NDIS_STATUS NdisFSynchronousOidRequest(
  _In_ NDIS_HANDLE      NdisFilterModuleHandle,
  _In_ NDIS_OID_REQUEST OidRequest
);
````

## Parameters

`NdisFilterModuleHandle`

Reserved.

`OidRequest`

Reserved.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |