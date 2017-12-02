---
UID: NF.ndis.NdisCoCreateVc
title: NdisCoCreateVc
author: windows-driver-content
description: NdisCoCreateVc sets up a connection endpoint from which a client can make outgoing calls or on which a stand-alone call manager can dispatch incoming calls.
old-location: netvista\ndiscocreatevc.htm
old-project: netvista
ms.assetid: ae9175e5-c1fc-44ae-a7c9-921ac8483e33
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisCoCreateVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCoCreateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCoCreateVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCoCreateVc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# NdisCoCreateVc function



## -description
<p><b>NdisCoCreateVc</b> sets up a connection endpoint from which a client can make outgoing calls or on which
  a stand-alone call manager can dispatch incoming calls.</p>


## -syntax

````
NDIS_STATUS NdisCoCreateVc(
  _In_     NDIS_HANDLE  NdisBindingHandle,
  _In_opt_ NDIS_HANDLE  NdisAfHandle,
  _In_     NDIS_HANDLE  ProtocolVcContext,
  _Inout_  PNDIS_HANDLE NdisVcHandle
);
````


## -parameters
<dl>

### -param NdisBindingHandle [in]

<dd>
<p>Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> that identifies the
     target NIC or virtual adapter of the next-lower driver to which the caller is bound.</p>
</dd>

### -param NdisAfHandle [in, optional]

<dd>
<p>Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a> if
     the caller is a client. A call manager sets this parameter to <b>NULL</b> if it is creating a VC for itself,
     such as a VC to a network switch. When it creates a VC for incoming call notifications, a call manager
     passes the AF handle that it saved in its per-AF state designated by the 
     <i>CallMgrAfContext</i> that was passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol-cm-reg-sap.md">
     ProtocolCmRegisterSap</a> function.</p>
</dd>

### -param ProtocolVcContext [in]

<dd>
<p>Specifies the handle to a caller-supplied resident context area in which the caller maintains
     state for this VC. NDIS passes this handle back to the VC creator in all subsequent calls concerning
     this endpoint if the call to 
     <b>NdisCoCreateVc</b> succeeds.</p>
</dd>

### -param NdisVcHandle [in, out]

<dd>
<p>Pointer to a caller-supplied variable that must be initialized to <b>NULL</b> when 
     <b>NdisCoCreateVc</b> is called. On return from a successful call, this points to a variable that NDIS
     has set to its handle for the newly created VC. The caller must save this handle for subsequent calls to
     connection-oriented Ndis
     <i>Xxx</i> functions.</p>
</dd>
</dl>

## -returns
<p><b>NdisCoCreateVc</b> can return one of the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>NDIS created the VC successfully.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p>NDIS could not allocate sufficient memory to set up the VC.</p><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><p>The given 
       <i>NdisAfHandle</i> is invalid.</p><dl>
<dt><b>NDIS_STATUS_
       <i>XXX</i></b></dt>
</dl><p>The underlying miniport driver failed the creation of the VC for a miniport driver-determined
       reason, which NDIS has propagated to the caller.</p>

<p> </p>

## -remarks
<p>A client or stand-alone call manager creates a VC with 
    <b>NdisCoCreateVc</b>, depending on whether the VC represents an outgoing or incoming call,
    respectively.</p>

<p>In the process of VC creation, NDIS supplies an 
    <i>NdisVcHandle</i> to the client, the call manager, and the miniport driver to which both protocol
    drivers are bound. This handle identifies the virtual circuit for the client, call manager, and miniport
    driver to which subsequent requests concerning the given VC are directed. Each driver must treat this VC
    handle as an opaque variable, passing it unmodified and uninterpreted in subsequent calls to certain
    connection-oriented NDIS library functions.</p>

<p>Usually, callers of 
    <b>NdisCoCreateVc</b> store the returned 
    <i>NdisVcHandle</i> in the caller-allocated state area at 
    <i>ProtocolVcContext</i> . NDIS passes this handle as an input parameter to the 
    <a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a> and 
    <a href="..\ndis\nc-ndis-miniport-co-create-vc.md">MiniportCoCreateVc</a> functions of the
    other two drivers involved in each creation of a VC.</p>

<p>To make an outgoing call, a client must call 
    <b>NdisCoCreateVc</b> first. As a synchronous operation, NDIS calls the underlying miniport driver's 
    <i>MiniportCoCreateVc</i> function and the call manager's 
    <i>ProtocolCoCreateVc</i> function before 
    <b>NdisCoCreateVc</b> returns control. If its call to 
    <b>NdisCoCreateVc</b> succeeds, the client can proceed in making an outgoing call, passing the returned 
    <i>NdisVcHandle</i> to 
    <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.</p>

<p>When its 
    <a href="..\ndis\nc-ndis-protocol-co-receive-net-buffer-lists.md">
    ProtocolCoReceiveNetBufferLists</a> function processes the offer of an incoming call directed to one of
    its registered SAPs, a call manager must call 
    <b>NdisCoCreateVc</b> first. As a synchronous operation, NDIS calls the underlying miniport driver's 
    <i>MiniportCoCreateVc</i> function and the client's 
    <i>ProtocolCoCreateVc</i> function before 
    <b>NdisCoCreateVc</b> returns control. If its call to 
    <b>NdisCoCreateVc</b> succeeds, the call manager can proceed in notifying the appropriate client, passing
    the returned value at 
    <i>NdisVcHandle</i> to 
    <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
    NdisCmDispatchIncomingCall</a>.</p>

<p>Stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCoCreateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>, instead.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff551026">NdisCoCreateVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCoCreateVc (NDIS 5.1)</b>) in
   Windows XP.</p>
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
<a href="devtest.ndis_irql_connection_function">Irql_Connection_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-co-create-vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-cm-reg-sap.md">ProtocolCmRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-receive-net-buffer-lists.md">
   ProtocolCoReceiveNetBufferLists</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoCreateVc function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
