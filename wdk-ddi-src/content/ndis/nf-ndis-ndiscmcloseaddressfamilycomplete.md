---
UID : NF:ndis.NdisCmCloseAddressFamilyComplete
title : NdisCmCloseAddressFamilyComplete function
author : windows-driver-content
description : NdisCmCloseAddressFamilyComplete returns the final status of a client's request, for which the CM's ProtocolCmCloseAf function returned NDIS_STATUS_PENDING, to close the AF.
old-location : netvista\ndiscmcloseaddressfamilycomplete.htm
old-project : netvista
ms.assetid : 1aeb2ca5-8c56-4a78-8cd5-a178efa9b014
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisCmCloseAddressFamilyComplete, NdisCmCloseAddressFamilyComplete, condis_call_manager_ref_e8f3c7fa-1a6a-4cf4-9c3c-78f036c2e912.xml, NdisCmCloseAddressFamilyComplete function [Network Drivers Starting with Windows Vista], netvista.ndiscmcloseaddressfamilycomplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_CallManager_Function
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


# NdisCmCloseAddressFamilyComplete function
<b>NdisCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the CM's 
  <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function returned
  NDIS_STATUS_PENDING, to close the AF.

## Syntax

````
VOID NdisCmCloseAddressFamilyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisAfHandle
);
````

## Parameters

`Status`

The call manager sets this to NDIS_STATUS_SUCCESS.

`NdisAfHandle`

Specifies the NDIS-supplied handle passed to the call manager's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


## Return Value

None

## Remarks

A stand-alone call manager must call 
    <b>NdisCmCloseAddressFamilyComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the CM's call to 
    <b>NdisCmCloseAddressFamilyComplete</b> causes a call to that client's 
    <mshelp:link keywords="netvista.protocolclcloseafcomplete" tabindex="0"><i>
    ProtocolClCloseAfComplete</i></mshelp:link> function.

After a call to 
    <b>NdisCmCloseAddressFamilyComplete</b>, the call manager cannot subsequently use the 
    <i>NdisAfHandle</i>, which becomes invalid for the call manager as soon as this call occurs.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmCloseAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> instead.

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
| **DDI compliance rules** | Irql_CallManager_Function |

## See Also

<mshelp:link keywords="netvista.ndismcmcloseaddressfamilycomplete" tabindex="0"><b>
   NdisMCmCloseAddressFamilyComplete</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>

<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>

<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>

<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmCloseAddressFamilyComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>