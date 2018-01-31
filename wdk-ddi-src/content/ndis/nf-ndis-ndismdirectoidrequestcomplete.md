---
UID : NF:ndis.NdisMDirectOidRequestComplete
title : NdisMDirectOidRequestComplete function
author : windows-driver-content
description : Miniport drivers call the NdisMDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's MiniportDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location : netvista\ndismdirectoidrequestcomplete.htm
old-project : netvista
ms.assetid : 11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisMDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], NdisMDirectOidRequestComplete, ndis/NdisMDirectOidRequestComplete, ndis_request_direct_ref_5f09825b-962f-41a9-b25d-e21c20e23249.xml, netvista.ndismdirectoidrequestcomplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
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


# NdisMDirectOidRequestComplete function
Miniport drivers call the 
  <b>NdisMDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <mshelp:link keywords="netvista.miniportdirectoidrequest" tabindex="0"><i>
  MiniportDirectOidRequest</i></mshelp:link> function returned NDIS_STATUS_PENDING.

## Syntax

````
VOID NdisMDirectOidRequestComplete(
  _In_ NDIS_HANDLE       MiniportAdapterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
);
````

## Parameters

`MiniportAdapterHandle`

A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.

`OidRequest`

A pointer to a buffer that is formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportDirectOidRequest</i> function.

`Status`

The final status of the request operation: NDIS_STATUS_SUCCESS, NDIS_STATUS_REQUEST_ABORTED, or
     any driver-determined NDIS_STATUS_<i>Xxx</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <mshelp:link keywords="netvista.miniportdirectoidrequest" tabindex="0"><i>
     MiniportDirectOidRequest</i></mshelp:link>.


## Return Value

None

## Remarks

A miniport driver that returns NDIS_STATUS_PENDING from its 
    <mshelp:link keywords="netvista.miniportdirectoidrequest" tabindex="0"><i>
    MiniportDirectOidRequest</i></mshelp:link> function must call 
    <b>NdisMDirectOidRequestComplete</b> after the miniport driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <mshelp:link keywords="netvista.protocoldirectoidrequestcomplete" tabindex="0"><i>
    ProtocolDirectOidRequestComplete</i></mshelp:link> and 
    <mshelp:link keywords="netvista.filterdirectoidrequestcomplete" tabindex="0"><i>
    FilterDirectOidRequestComplete</i></mshelp:link>) of the overlying that originated the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.protocoldirectoidrequestcomplete" tabindex="0"><i>
   ProtocolDirectOidRequestComplete</i></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nc-ndis-miniport_direct_oid_request.md">MiniportDirectOidRequest</a>

<mshelp:link keywords="netvista.filterdirectoidrequestcomplete" tabindex="0"><i>
   FilterDirectOidRequestComplete</i></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDirectOidRequestComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>