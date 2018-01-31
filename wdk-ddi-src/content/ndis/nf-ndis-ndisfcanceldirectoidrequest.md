---
UID : NF:ndis.NdisFCancelDirectOidRequest
title : NdisFCancelDirectOidRequest function
author : windows-driver-content
description : Filter drivers call the NdisFCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location : netvista\ndisfcanceldirectoidrequest.htm
old-project : netvista
ms.assetid : 05cbeca1-7420-41c6-8868-980b265523db
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisFCancelDirectOidRequest, ndis/NdisFCancelDirectOidRequest, NdisFCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], netvista.ndisfcanceldirectoidrequest, ndis_request_direct_ref_48dc16f9-1c11-41de-9c37-91abed86b06c.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.1 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFCancelDirectOidRequest function
Filter drivers call the 
  <b>NdisFCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.

## Syntax

````
VOID NdisFCancelDirectOidRequest(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ PVOID       RequestId
);
````

## Parameters

`NdisFilterHandle`

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`RequestId`

A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## Return Value

None

## Remarks

Filter drivers call 
    <b>NdisFCancelDirectOidRequest</b> to cancel a previously issued direct OID request. The request can be
    originated by the filter driver or by overlying drivers. The pointer that is passed at the 
    <i>OidRequest</i> parameter must be the same pointer that was passed in the call to the 
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelDirectOidRequest</b> from the 
    <mshelp:link keywords="netvista.filtercanceldirectoidrequest" tabindex="0"><i>
    FilterCancelDirectOidRequest</i></mshelp:link> function to pass on the cancellation to underlying drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a>

<mshelp:link keywords="netvista.filtercanceldirectoidrequest" tabindex="0"><i>
   FilterCancelDirectOidRequest</i></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelDirectOidRequest function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>