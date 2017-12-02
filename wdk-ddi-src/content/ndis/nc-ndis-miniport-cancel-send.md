---
UID: NC.ndis.MINIPORT_CANCEL_SEND
title: MINIPORT_CANCEL_SEND
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportCancelSend function to cancel the transmission of all NET_BUFFER_LIST structures that are marked with a specified cancellation identifier.
old-location: netvista\miniportcancelsend.htm
old-project: netvista
ms.assetid: 17111aa3-c02f-494a-af97-5ab34c152451
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportCancelSend
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# MINIPORT_CANCEL_SEND callback



## -description
<p>NDIS calls a miniport driver's 
   <i>MiniportCancelSend</i> function to cancel the transmission of all 
   <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures that are marked
   with a specified cancellation identifier.</p>


## -prototype

````
MINIPORT_CANCEL_SEND MiniportCancelSend;

VOID MiniportCancelSend(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ PVOID       CancelId
)
{ ... }
````


## -parameters
<dl>

### -param MiniportAdapterContext [in]

<dd>
<p>A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information about an adapter.</p>
</dd>

### -param CancelId [in]

<dd>
<p>A cancellation identifier. This identifier specifies the <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures that are being
     canceled.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Miniport drivers and intermediate drivers that queue send 
    <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures export a 
    <i>MiniportCancelSend</i> function. The 
    <i>MiniportCancelSend</i> function cancels the pending transmission of the specified NET_BUFFER_LIST
    structures.</p>

<p>When an overlying NDIS driver calls the 
    <a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">
    NdisCancelSendNetBufferLists</a> function, NDIS calls the 
    <i>MiniportCancelSend</i> function of the appropriate lower-level driver on the binding. NDIS makes this
    call only if the lower-level driver exports a 
    <i>MiniportCancelSend</i> function.</p>

<p>A miniport driver's 
    <i>MiniportCancelSend</i> function performs the following operations:</p>

<p>Traverses its list of queued NET_BUFFER_LIST structures for the specified adapter and calls the 
      <a href="netvista.ndis_get_net_buffer_list_cancel_id">
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a> macro to obtain the cancellation identifier for each queued
      NET_BUFFER_LIST structure. The miniport driver compares the cancellation identifier that
      NDIS_GET_NET_BUFFER_LIST_CANCEL_ID returns with the cancellation identifier that NDIS passed to 
      <i>MiniportCancelSend</i>.</p>

<p>Removes from the send queue (un-links) all NET_BUFFER_LIST structures whose cancellation identifiers
      match the specified cancellation identifier.</p>

<p>Calls the 
      <a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
      NdisMSendNetBufferListsComplete</a> function for all unlinked NET_BUFFER_LIST structures to return
      the structures .The miniport driver sets the status field of the NET_BUFFER_LIST structures to
      NDIS_STATUS_SEND_ABORTED.</p>

<p>An intermediate driver's 
    <i>MiniportCancelSend</i> function performs the following operations:</p>

<p>Performs the operations in the preceding list for a miniport driver's
      <i>MiniportCancelSend</i> function.</p>

<p>Calls the 
      <a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">
      NdisCancelSendNetBufferLists</a> function, specifying the binding that maps to the adapter that NDIS
      specified in the call to 
      <i>MiniportCancelSend</i>.</p>

<p>NDIS calls 
    <i>MiniportCancelSend</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>MiniportCancelSend</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportCancelSend</i> function that is named "MyCancelSend", use the <b>MINIPORT_CANCEL_SEND</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_CANCEL_SEND</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_SEND</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
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
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndis_get_net_buffer_list_cancel_id">
   NDIS_GET_NET_BUFFER_LIST_CANCEL_ID</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscancelsendnetbufferlists.md">NdisCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
   NdisMSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CANCEL_SEND callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
