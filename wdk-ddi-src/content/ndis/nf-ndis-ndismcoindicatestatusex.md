---
UID: NF.ndis.NdisMCoIndicateStatusEx
title: NdisMCoIndicateStatusEx function
author: windows-driver-content
description: The NdisMCoIndicateStatusEx function reports a change in the status of a CoNDIS miniport adapter.
old-location: netvista\ndismcoindicatestatusex.htm
old-project: netvista
ms.assetid: e6d5bd94-d9cb-462f-84e4-bf9d70961e95
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMCoIndicateStatusEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCoIndicateStatusEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_MCO_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMCoIndicateStatusEx function



## -description
The 
  <b>NdisMCoIndicateStatusEx</b> function reports a change in the status of a CoNDIS miniport adapter.


## -syntax

````
VOID NdisMCoIndicateStatusEx(
  _In_     NDIS_HANDLE             MiniportAdapterHandle,
  _In_opt_ NDIS_HANDLE             NdisVcHandle,
  _In_     PNDIS_STATUS_INDICATION StatusIndication
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

### -param NdisVcHandle [in, optional]

A handle that identifies the virtual connection (VC). The miniport driver obtained this handle as
     an input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP). The call manager created the VC to indicate an incoming-call notification.
     To send the status indication to all protocol bindings, set this parameter to <b>NULL</b>.

### -param StatusIndication [in]

A pointer to an 
     <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.

## -returns
None

## -remarks
When a miniport driver calls 
    <b>NdisMCoIndicateStatusEx</b> with a <b>NULL</b> VC handle for the 
    <i>NdisVcHandle</i> parameter, NDIS forwards the status-change notification to all of the bound protocol
    drivers by calling each bound protocol driver's 
    <a href="..\ndis\nc-ndis-protocol_co_status_ex.md">ProtocolCoStatusEx</a> function. A call
    to 
    <b>NdisMCoIndicateStatusEx</b> with a non-<b>NULL</b> VC handle restricts the status notification to clients or
    call managers that the miniport driver shares this VC handle with.

A miniport driver can call 
    <b>NdisMCoIndicateStatusEx</b> after setting its registration attributes, by calling the 
    <a href="netvista.ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function,
    even if the driver is still in the context of the 
    <i>MiniportInitializeEx</i> function. The driver must not call 
    <b>NdisMCoIndicateStatusEx</b> after it returns from the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_mco_function">Irql_MCO_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_status_ex.md">ProtocolCoStatusEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoIndicateStatusEx function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
