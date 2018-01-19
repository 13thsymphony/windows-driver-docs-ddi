---
UID : NF:ndis.NdisCmNotifyCloseAddressFamily
title : NdisCmNotifyCloseAddressFamily function
author : windows-driver-content
description : The NdisCmNotifyCloseAddressFamily function notifies NDIS that a call manager is unbinding from an underlying miniport adapter and that any associated CoNDIS clients should close the specified address family (AF).
old-location : netvista\ndiscmnotifycloseaddressfamily.htm
old-project : netvista
ms.assetid : 1967f663-86ce-4e9d-9498-61951bdf4db0
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisCmNotifyCloseAddressFamily
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisCmNotifyCloseAddressFamily
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_CallManager_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCmNotifyCloseAddressFamily function
The 
  <b>NdisCmNotifyCloseAddressFamily</b> function notifies NDIS that a call manager is unbinding from an
  underlying miniport adapter and that any associated CoNDIS clients should close the specified address
  family (AF).

## Syntax

````
NDIS_STATUS NdisCmNotifyCloseAddressFamily(
  _In_ NDIS_HANDLE NdisAfHandle
);
````

## Parameters

`NdisAfHandle`

An NDIS handle that identifies the AF that NDIS should close. NDIS supplied this handle to the
     call manager's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


## Return Value

<b>NdisCmNotifyCloseAddressFamily</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>NDIS successfully closed the address family.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>NDIS is handling this request asynchronously, and it will call the call manager's 
       <a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
       ProtocolCmNotifyCloseAfComplete</a> function when the close operation is complete.
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>NDIS failed the request for some NDIS or client driver-determined reason.

## Remarks

Stand-alone CoNDIS call managers, which register as NDIS protocol drivers by calling the 
    <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
    NdisRegisterProtocolDriver</a> function, can call the 
    <b>NdisCmNotifyCloseAddressFamily</b> function. Miniport call managers (MCMs) instead call the 
    <a href="..\ndis\nf-ndis-ndismcmnotifycloseaddressfamily.md">
    NdisMCmNotifyCloseAddressFamily</a> function.

To close an AF for a binding, the stand-alone call manager should call 
    <b>NdisCmNotifyCloseAddressFamily</b> from the 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function. NDIS then calls the 
    <a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">
    ProtocolClNotifyCloseAf</a> function of the client that has the specified AF open.

If 
    <b>NdisCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls the call manager's 
    <a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
    ProtocolCmNotifyCloseAfComplete</a> function after the client completes the AF close operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_CallManager_Function |

## See Also

<dl>
<dt>
<a href="..\ndis\nf-ndis-ndismcmnotifycloseaddressfamily.md">
   NdisMCmNotifyCloseAddressFamily</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">ProtocolClNotifyCloseAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
   ProtocolCmNotifyCloseAfComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmNotifyCloseAddressFamily function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>