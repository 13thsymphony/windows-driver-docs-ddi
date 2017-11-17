---
UID: NF.ndis.NdisMCoIndicateStatusEx
title: NdisMCoIndicateStatusEx
author: windows-driver-content
description: The NdisMCoIndicateStatusEx function reports a change in the status of a CoNDIS miniport adapter.
old-location: netvista\ndismcoindicatestatusex.htm
ms.assetid: e6d5bd94-d9cb-462f-84e4-bf9d70961e95
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
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
ms.keywords: NdisMCoIndicateStatusEx
req.iface: 
---

# NdisMCoIndicateStatusEx function



## -description
<p>The 
  <b>NdisMCoIndicateStatusEx</b> function reports a change in the status of a CoNDIS miniport adapter.</p>


## -syntax

````
VOID NdisMCoIndicateStatusEx(
  _In_     NDIS_HANDLE             MiniportAdapterHandle,
  _In_opt_ NDIS_HANDLE             NdisVcHandle,
  _In_     PNDIS_STATUS_INDICATION StatusIndication
);
````


## -parameters
<dl>

### -param <i>MiniportAdapterHandle</i> [in]

<dd>
<p>The miniport adapter handle that NDIS passed at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.</p>
</dd>

### -param <i>NdisVcHandle</i> [in, optional]

<dd>
<p>A handle that identifies the virtual connection (VC). The miniport driver obtained this handle as
     an input parameter to its 
     <a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP). The call manager created the VC to indicate an incoming-call notification.
     To send the status indication to all protocol bindings, set this parameter to <b>NULL</b>.</p>
</dd>

### -param <i>StatusIndication</i> [in]

<dd>
<p>A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>When a miniport driver calls 
    <b>NdisMCoIndicateStatusEx</b> with a <b>NULL</b> VC handle for the 
    <i>NdisVcHandle</i> parameter, NDIS forwards the status-change notification to all of the bound protocol
    drivers by calling each bound protocol driver's 
    <a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a> function. A call
    to 
    <b>NdisMCoIndicateStatusEx</b> with a non-<b>NULL</b> VC handle restricts the status notification to clients or
    call managers that the miniport driver shares this VC handle with.</p>

<p>A miniport driver can call 
    <b>NdisMCoIndicateStatusEx</b> after setting its registration attributes, by calling the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function,
    even if the driver is still in the context of the 
    <i>MiniportInitializeEx</i> function. The driver must not call 
    <b>NdisMCoIndicateStatusEx</b> after it returns from the 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function.</p>

<p>When a miniport driver calls 
    <b>NdisMCoIndicateStatusEx</b> with a <b>NULL</b> VC handle for the 
    <i>NdisVcHandle</i> parameter, NDIS forwards the status-change notification to all of the bound protocol
    drivers by calling each bound protocol driver's 
    <a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a> function. A call
    to 
    <b>NdisMCoIndicateStatusEx</b> with a non-<b>NULL</b> VC handle restricts the status notification to clients or
    call managers that the miniport driver shares this VC handle with.</p>

<p>A miniport driver can call 
    <b>NdisMCoIndicateStatusEx</b> after setting its registration attributes, by calling the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function,
    even if the driver is still in the context of the 
    <i>MiniportInitializeEx</i> function. The driver must not call 
    <b>NdisMCoIndicateStatusEx</b> after it returns from the 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547971">Irql_MCO_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoIndicateStatusEx function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
