---
UID: NF:ndis.NdisFCancelDirectOidRequest
title: NdisFCancelDirectOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndisfcanceldirectoidrequest.htm
old-project: netvista
ms.assetid: 05cbeca1-7420-41c6-8868-980b265523db
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFCancelDirectOidRequest, NdisFCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFCancelDirectOidRequest, ndis_request_direct_ref_48dc16f9-1c11-41de-9c37-91abed86b06c.xml, netvista.ndisfcanceldirectoidrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFCancelDirectOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFCancelDirectOidRequest function
Filter drivers call the 
  <b>NdisFCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.

## Syntax

```
void NdisFCancelDirectOidRequest(
  NDIS_HANDLE NdisFilterHandle,
  PVOID       RequestId
);
```

## Parameters

`NdisFilterHandle`

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.

`RequestId`

A cancellation identifier for the request. This identifier specifies the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## Return Value

None

## Remarks

Filter drivers call 
    <b>NdisFCancelDirectOidRequest</b> to cancel a previously issued direct OID request. The request can be
    originated by the filter driver or by overlying drivers. The pointer that is passed at the 
    <i>OidRequest</i> parameter must be the same pointer that was passed in the call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelDirectOidRequest</b> from the 
    <a href="https://msdn.microsoft.com/3587c5dc-3b4c-4aab-8c2d-cc9988373a56">
    FilterCancelDirectOidRequest</a> function to pass on the cancellation to underlying drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.1 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/3587c5dc-3b4c-4aab-8c2d-cc9988373a56">
   FilterCancelDirectOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a>