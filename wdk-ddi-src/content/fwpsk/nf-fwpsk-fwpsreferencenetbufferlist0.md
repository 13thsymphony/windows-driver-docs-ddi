---
UID: NF:fwpsk.FwpsReferenceNetBufferList0
title: FwpsReferenceNetBufferList0 function
author: windows-driver-content
description: The FwpsReferenceNetBufferList0 function increments the reference count for a NET_BUFFER_LIST structure.Note  FwpsReferenceNetBufferList0 is a specific version of FwpsReferenceNetBufferList.
old-location: netvista\fwpsreferencenetbufferlist0.htm
old-project: netvista
ms.assetid: ff387b49-fecb-41d0-aac5-0a83eb8835d6
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpsReferenceNetBufferList0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsReferenceNetBufferList0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsReferenceNetBufferList0 function



## -description
The 
  <b>FwpsReferenceNetBufferList0</b> function increments the reference count for a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



## -syntax

````
void NTAPI FwpsReferenceNetBufferList0(
  _Inout_ NET_BUFFER_LIST *netBufferList,
  _In_    BOOLEAN         intendToModify
);
````


## -parameters

### -param netBufferList [in, out]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for which the
     reference count is being incremented.


### -param intendToModify [in]

A value that indicates whether a callout intends to modify the cloned network buffer list, whose
     parent is pointed to by the 
     <i>netBufferList</i> parameter, after the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function has returned. If <b>TRUE</b>,
     the callout intends to modify the cloned net buffer list after 
     <i>classifyFn</i> has returned (an out-of-band modification). Otherwise, set to <b>FALSE</b>.


## -returns
None.


## -remarks
A callout driver calls the 
    <b>FwpsReferenceNetBufferList0</b> function to increment the reference count for a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure such that the network
    buffer list remains valid outside of the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function.

For example, when a callout driver performs packet reassembly, it increments the reference count for
    each of the received NET_BUFFER_LIST structures that describe the packet fragments that make up an
    individual packet. This allows the new NET_BUFFER_LIST structure that describes the reassembled packet to
    safely reference the memory descriptor lists (MDLs) pointed to by the NET_BUFFER_LIST structures that describe the packet
    fragments. After the callout driver has injected the new NET_BUFFER_LIST structure into the network
    stack, it decrements the reference count for each of the NET_BUFFER_LIST structures that describe the
    packet fragments from its packet injection completion routine.

A callout driver must call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsdereferencenetbufferlist0.md">FwpsDereferenceNetBufferList0</a> function for the NET_BUFFER_LIST structure after the callout driver
    has finished referencing the structure.

A callout driver must not hold referenced packets indefinitely. A referenced packet can interfere
     with power management operations on an idle computer.

The intended use for referenced packets in WFP is to get clarification from a user-mode application
     or other relatively fast operation. The callout driver must not hold referenced packets while, for
     example, waiting for user input, web service clearance, or any other
     operation that might take an arbitrary amount of time.

If the callout driver must wait for a potentially lengthy operation, it should make a deep copy of
     the packet using 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> and block and absorb the original packet.

Callout drivers should always return held packets as quickly as possible.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsdereferencenetbufferlist0.md">
   FwpsDereferenceNetBufferList0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsReferenceNetBufferList0 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

