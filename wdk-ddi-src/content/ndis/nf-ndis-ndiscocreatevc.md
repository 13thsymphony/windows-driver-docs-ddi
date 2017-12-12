---
UID: NF.ndis.NdisCoCreateVc
title: NdisCoCreateVc function
author: windows-driver-content
description: NdisCoCreateVc sets up a connection endpoint from which a client can make outgoing calls or on which a stand-alone call manager can dispatch incoming calls.
old-location: netvista\ndiscocreatevc.htm
old-project: netvista
ms.assetid: ae9175e5-c1fc-44ae-a7c9-921ac8483e33
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
---

# NdisCoCreateVc function



## -description
<b>NdisCoCreateVc</b> sets up a connection endpoint from which a client can make outgoing calls or on which
  a stand-alone call manager can dispatch incoming calls.



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

### -param NdisBindingHandle [in]

Specifies the handle returned by 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> that identifies the
     target NIC or virtual adapter of the next-lower driver to which the caller is bound.


### -param NdisAfHandle [in, optional]

Specifies the handle returned by 
     <a href="netvista.ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a> if
     the caller is a client. A call manager sets this parameter to <b>NULL</b> if it is creating a VC for itself,
     such as a VC to a network switch. When it creates a VC for incoming call notifications, a call manager
     passes the AF handle that it saved in its per-AF state designated by the 
     <i>CallMgrAfContext</i> that was passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


### -param ProtocolVcContext [in]

Specifies the handle to a caller-supplied resident context area in which the caller maintains
     state for this VC. NDIS passes this handle back to the VC creator in all subsequent calls concerning
     this endpoint if the call to 
     <b>NdisCoCreateVc</b> succeeds.


### -param NdisVcHandle [in, out]

Pointer to a caller-supplied variable that must be initialized to <b>NULL</b> when 
     <b>NdisCoCreateVc</b> is called. On return from a successful call, this points to a variable that NDIS
     has set to its handle for the newly created VC. The caller must save this handle for subsequent calls to
     connection-oriented Ndis
     <i>Xxx</i> functions.


## -returns
<b>NdisCoCreateVc</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>NDIS created the VC successfully.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>NDIS could not allocate sufficient memory to set up the VC.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The given 
       <i>NdisAfHandle</i> is invalid.
<dl>
<dt><b>NDIS_STATUS_
       <i>XXX</i></b></dt>
</dl>The underlying miniport driver failed the creation of the VC for a miniport driver-determined
       reason, which NDIS has propagated to the caller.

 


## -remarks
A client or stand-alone call manager creates a VC with 
    <b>NdisCoCreateVc</b>, depending on whether the VC represents an outgoing or incoming call,
    respectively.

In the process of VC creation, NDIS supplies an 
    <i>NdisVcHandle</i> to the client, the call manager, and the miniport driver to which both protocol
    drivers are bound. This handle identifies the virtual circuit for the client, call manager, and miniport
    driver to which subsequent requests concerning the given VC are directed. Each driver must treat this VC
    handle as an opaque variable, passing it unmodified and uninterpreted in subsequent calls to certain
    connection-oriented NDIS library functions.

Usually, callers of 
    <b>NdisCoCreateVc</b> store the returned 
    <i>NdisVcHandle</i> in the caller-allocated state area at 
    <i>ProtocolVcContext</i> . NDIS passes this handle as an input parameter to the 
    <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> and 
    <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> functions of the
    other two drivers involved in each creation of a VC.

To make an outgoing call, a client must call 
    <b>NdisCoCreateVc</b> first. As a synchronous operation, NDIS calls the underlying miniport driver's 
    <i>MiniportCoCreateVc</i> function and the call manager's 
    <i>ProtocolCoCreateVc</i> function before 
    <b>NdisCoCreateVc</b> returns control. If its call to 
    <b>NdisCoCreateVc</b> succeeds, the client can proceed in making an outgoing call, passing the returned 
    <i>NdisVcHandle</i> to 
    <a href="netvista.ndisclmakecall">NdisClMakeCall</a>.

When its 
    <a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
    ProtocolCoReceiveNetBufferLists</a> function processes the offer of an incoming call directed to one of
    its registered SAPs, a call manager must call 
    <b>NdisCoCreateVc</b> first. As a synchronous operation, NDIS calls the underlying miniport driver's 
    <i>MiniportCoCreateVc</i> function and the client's 
    <i>ProtocolCoCreateVc</i> function before 
    <b>NdisCoCreateVc</b> returns control. If its call to 
    <b>NdisCoCreateVc</b> succeeds, the call manager can proceed in notifying the appropriate client, passing
    the returned value at 
    <i>NdisVcHandle</i> to 
    <a href="netvista.ndiscmdispatchincomingcall">
    NdisCmDispatchIncomingCall</a>.

Stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCoCreateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>, instead.


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
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff551026">NdisCoCreateVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCoCreateVc (NDIS 5.1)</b>) in
   Windows XP.

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
<a href="devtest.ndis_irql_connection_function">Irql_Connection_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="netvista.ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisclmakecall">NdisClMakeCall</a>
</dt>
<dt>
<a href="netvista.ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="netvista.ndiscodeletevc">NdisCoDeleteVc</a>
</dt>
<dt>
<a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
   ProtocolCoReceiveNetBufferLists</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoCreateVc function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

