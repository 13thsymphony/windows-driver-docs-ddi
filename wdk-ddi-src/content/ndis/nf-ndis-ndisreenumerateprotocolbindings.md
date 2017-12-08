---
UID: NF.ndis.NdisReEnumerateProtocolBindings
title: NdisReEnumerateProtocolBindings function
author: windows-driver-content
description: The NdisReEnumerateProtocolBindings function causes NDIS to call a protocol driver's ProtocolBindAdapterEx function one time for each miniport adapter for which the driver is configured to bind but to which the driver is not currently bound.
old-location: netvista\ndisreenumerateprotocolbindings.htm
old-project: netvista
ms.assetid: e47d812b-2fbb-44c4-a441-bd30ae89a5eb
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisReEnumerateProtocolBindings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisReEnumerateProtocolBindings (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisReEnumerateProtocolBindings (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisReEnumerateProtocolBindings
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function, NdisReEnumerateProtocolBindings
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisReEnumerateProtocolBindings function



## -description
The 
  <b>NdisReEnumerateProtocolBindings</b> function causes NDIS to call a protocol driver's 
  <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function one
  time for each miniport adapter for which the driver is configured to bind but to which the driver is not
  currently bound.


## -syntax

````
VOID NdisReEnumerateProtocolBindings(
  _In_ NDIS_HANDLE NdisProtocolHandle
);
````


## -parameters

### -param NdisProtocolHandle [in]

A handle representing the calling protocol driver. The driver obtained this handle with a previous
     call to the 
     <a href="netvista.ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> function.

## -returns
None

## -remarks
A protocol driver can call the 
    <b>NdisReEnumerateProtocolBindings</b> function to rebind to one or more miniport adapters.

Protocol drivers cannot call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of the 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>, or 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> functions. Also, protocol drivers cannot call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of the 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function if the
    
    <i>ProtocolBindingContext</i> parameter of 
    <i>ProtocolNetPnPEvent</i> is not <b>NULL</b>. However, protocol drivers can call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of 
    <i>ProtocolNetPnPEvent</i> if 
    <i>ProtocolBindingContext</i> is <b>NULL</b>. A <b>NULL</b><i>ProtocolBindingContext</i> value indicates that the event applies to all bindings.

NDIS might complete the binding operations after the call to 
    <b>NdisReEnumerateProtocolBindings</b> returns. That is, NDIS might complete bindings to the miniport
    adapters for which the protocol driver is configured to bind but to which the protocol driver is not
    currently bound at a later time.

An intermediate driver should call 
    <b>NdisReEnumerateProtocolBindings</b> after its 
    <i>ProtocolNetPnPEvent</i> function receives 
    <b>NetEventReconfigure</b> on a <b>NULL</b><i>ProtocolBindingContext</i> . NDIS then calls the driver's 
    <i>ProtocolBindAdapterEx</i> function one time for each miniport adapter for which the driver is
    configured to bind but to which the driver is not currently bound.

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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/b0354369-d1a3-4252-8ed8-d2fdcb376b50">
   NdisReEnumerateProtocolBindings (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisReEnumerateProtocolBindings (NDIS 5.1)</b>) in Windows XP.
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
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>, <a href="devtest.ndis_ndisreenumerateprotocolbindings">NdisReEnumerateProtocolBindings</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b2b2a15d-4183-4022-bb08-2d97aa26d4b1">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReEnumerateProtocolBindings function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
