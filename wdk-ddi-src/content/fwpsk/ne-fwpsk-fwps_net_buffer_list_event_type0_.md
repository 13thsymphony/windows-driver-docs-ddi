---
UID: NE.fwpsk.FWPS_NET_BUFFER_LIST_EVENT_TYPE0_
title: FWPS_NET_BUFFER_LIST_EVENT_TYPE0_
author: windows-driver-content
description: The FWPS_NET_BUFFER_LIST_EVENT_TYPE0 enumeration type specifies the possible status events that can cause the callout driver's FWPS_NET_BUFFER_LIST_NOTIFY_FN0 function to be called.Note  FWPS_NET_BUFFER_LIST_EVENT_TYPE0 is a specific version of FWPS_NET_BUFFER_LIST_EVENT_TYPE. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_net_buffer_list_event_type0.htm
old-project: netvista
ms.assetid: 14225920-2f51-4fef-9501-812e3aff8905
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FWPS_NET_BUFFER_LIST_EVENT_TYPE0_, FWPS_NET_BUFFER_LIST_EVENT_TYPE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise indicated, supported starting with  Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_NET_BUFFER_LIST_EVENT_TYPE0
req.alt-loc: fwpsk.h
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
---

# FWPS_NET_BUFFER_LIST_EVENT_TYPE0_ enumeration



## -description
The <b>FWPS_NET_BUFFER_LIST_EVENT_TYPE0</b> enumeration type specifies the possible status events that can
  cause the callout driver's 
  <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
  FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> function to be called.


## -syntax

````
typedef enum FWPS_NET_BUFFER_LIST_EVENT_TYPE0_ { 
  FWPS_NET_BUFFER_LIST_ENTERED_NETIO,
  FWPS_NET_BUFFER_LIST_CLONED_BY_NETIO,
  FWPS_NET_BUFFER_LIST_CLONED_VIA_WFP_API,
  FWPS_NET_BUFFER_LIST_DUPLICATED_BY_NETIO,
  FWPS_NET_BUFFER_LIST_EXIT_NETIO,
  FWPS_NET_BUFFER_LIST_CONTEXT_REMOVED,
  FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE,
#if (NTDDI_VERSION >= NTDDI_WIN8)
  FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE                                      = FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE                                      = FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_NATIVE_SEND_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_NATIVE_RECV_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_INGRESS_COMPLETE,
  FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETEFWPS_NET_BUFFER_LIST_CLONED_BY_NDIS,
  FWPS_NET_BUFFER_LIST_CLONED_BY_NDIS

#endif } FWPS_NET_BUFFER_LIST_EVENT_TYPE0;
````


## -enum-fields

### -field FWPS_NET_BUFFER_LIST_ENTERED_NETIO

The <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure entered the TCP/IP stack. Packets enter the stack either from
     the NDIS layer or as a result of a call to a WFP packet injection function.

### -field FWPS_NET_BUFFER_LIST_CLONED_BY_NETIO

The NET_BUFFER_LIST structure was cloned.

### -field FWPS_NET_BUFFER_LIST_CLONED_VIA_WFP_API

The NET_BUFFER_LIST structure was cloned by a call to the 
     <a href="netvista.fwpsallocateclonenetbufferlist0">FwpsAllocateCloneNetBufferList0</a> function.

### -field FWPS_NET_BUFFER_LIST_DUPLICATED_BY_NETIO

The NET_BUFFER_LIST structure was duplicated.

### -field FWPS_NET_BUFFER_LIST_EXIT_NETIO

The NET_BUFFER_LIST structure is about to leave the TCP/IP stack.

### -field FWPS_NET_BUFFER_LIST_CONTEXT_REMOVED

The NET_BUFFER_LIST structure is outside of the context for which it was tagged. The
     circumstances for this event depend upon the specifics of the tagged packets.
     
<table>
<tr>
<th>Packet Type</th>
<th>Event Condition</th>
</tr>
<tr>
<td>
Outbound
</td>
<td>
The NET_BUFFER_LIST structure exits the TCP/IP stack.
</td>
</tr>
<tr>
<td>
Any
</td>
<td>
Upon asynchronous context removal resulting from a call to the 
        <a href="netvista.fwpsnetbufferlistremovecontext0">
        FwpsNetBufferListRemoveContext0</a> function.
</td>
</tr>
</table>
 

### -field FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE

See FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE.

### -field FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE

See FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE.

### -field FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE

The NET_BUFFER_LIST structure send over the upper (protocol driver) NDIS 802.3 layer is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE

The NET_BUFFER_LIST structure receive over the upper (protocol driver) NDIS 802.3 layer is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_NATIVE_SEND_COMPLETE

The NET_BUFFER_LIST structure send over the lower (miniport driver) NDIS native layer is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_NATIVE_RECV_COMPLETE

The NET_BUFFER_LIST structure receive over the lower (miniport driver) NDIS  native layer is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_INGRESS_COMPLETE

The NET_BUFFER_LIST structure ingres on the virtual switch is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETEFWPS_NET_BUFFER_LIST_CLONED_BY_NDIS

The NET_BUFFER_LIST structure egress on the virtual switch is complete.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_CLONED_BY_NDIS

NDIS cloned the  NET_BUFFER_LIST structure.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Unless otherwise indicated, supported starting with  Windows Vista.
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
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn0.md">
  FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>
</dt>
<dt>
<a href="netvista.fwpsallocateclonenetbufferlist0">
     FwpsAllocateCloneNetBufferList0</a>
</dt>
<dt>
<a href="netvista.fwpsnetbufferlistremovecontext0">
        FwpsNetBufferListRemoveContext0</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_NET_BUFFER_LIST_EVENT_TYPE0 enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
