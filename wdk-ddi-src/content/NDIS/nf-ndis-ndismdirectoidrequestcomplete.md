---
UID: NF.ndis.NdisMDirectOidRequestComplete
title: NdisMDirectOidRequestComplete
author: windows-driver-content
description: Miniport drivers call the NdisMDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's MiniportDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismdirectoidrequestcomplete.htm
ms.assetid: 11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMDirectOidRequestComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisMDirectOidRequestComplete
req.iface: 
---

# NdisMDirectOidRequestComplete function



## -description
<p>Miniport drivers call the 
  <b>NdisMDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
  MiniportDirectOidRequest</a> function returned NDIS_STATUS_PENDING.</p>


## -syntax

````
VOID NdisMDirectOidRequestComplete(
  _In_ NDIS_HANDLE       MiniportAdapterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
);
````


## -parameters
<dl>

### -param <i>MiniportAdapterHandle</i> [in]

<dd>
<p>A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.</p>
</dd>

### -param <i>OidRequest</i> [in]

<dd>
<p>A pointer to a buffer that is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportDirectOidRequest</i> function.</p>
</dd>

### -param <i>Status</i> [in]

<dd>
<p>The final status of the request operation: NDIS_STATUS_SUCCESS, NDIS_STATUS_REQUEST_ABORTED, or
     any driver-determined NDIS_STATUS_<i>Xxx</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
     MiniportDirectOidRequest</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
    MiniportDirectOidRequest</a> function must call 
    <b>NdisMDirectOidRequestComplete</b> after the miniport driver has finished the request operation.</p>

<p>If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
    FilterDirectOidRequestComplete</a>) of the overlying that originated the request.</p>

<p>A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
    MiniportDirectOidRequest</a> function must call 
    <b>NdisMDirectOidRequestComplete</b> after the miniport driver has finished the request operation.</p>

<p>If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
    FilterDirectOidRequestComplete</a>) of the overlying that originated the request.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
   FilterDirectOidRequestComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">MiniportDirectOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
   ProtocolDirectOidRequestComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDirectOidRequestComplete function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
