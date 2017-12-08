---
UID: NS.NDIS._NDIS_RSC_NBL_INFO
title: _NDIS_RSC_NBL_INFO
author: windows-driver-content
description: The NDIS_RSC_NBL_INFO union specifies receive segment coalescing (RSC) counter information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_rsc_nbl_info.htm
old-project: netvista
ms.assetid: ba9c18ba-8940-4aef-9d58-3105ee1420ce
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_RSC_NBL_INFO, NDIS_RSC_NBL_INFO, *PNDIS_RSC_NBL_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.30 and later drivers in Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RSC_NBL_INFO
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
---

# _NDIS_RSC_NBL_INFO structure



## -description
The <b>NDIS_RSC_NBL_INFO</b> union specifies receive segment coalescing (RSC) counter information that is associated with a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.




## -syntax

````
typedef union _NDIS_RSC_NBL_INFO {
  struct {
    USHORT CoalescedSegCount;
    USHORT DupAckCount;
  } Info;
  PVOID  Value;
} NDIS_RSC_NBL_INFO, *PNDIS_RSC_NBL_INFO;
````


## -struct-fields

### -field Info

 
A member in the union that is contained in <b>NDIS_RSC_NBL_INFO</b>.  Drivers use <b>Info</b> to access RSC information. <b>Info</b> is a structure with the following members:



### -field CoalescedSegCount

The number of coalesced segments in the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. For non-RSC packets this member must be set to zero.
Drivers can access this member with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439944">NET_BUFFER_LIST_COALESCED_SEG_COUNT</a>
macro. 
<div class="alert"><b>Note</b>  The <b>RscTcpTimestampDelta</b> information  and the <b>DupAckCount</b> member should be non-zero only if <b>CoalescedSegCount</b> is not zero.
See the remarks section for more information about <b>RscTcpTimestampDelta</b>.</div>
<div> </div>

### -field DupAckCount

The number of duplicate ACKs that were encountered while forming the  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. <b>DupAckCount</b> should be non-zero only if <b>CoalescedSegCount</b> is not zero.
Drivers can access this member with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439945">NET_BUFFER_LIST_DUP_ACK_COUNT</a>
macro.
</dd>
</dl>

### -field Value

A member in the union that is contained in <b>NDIS_RSC_NBL_INFO</b>.  Drivers use <b>Value</b> to access the RSC information as a single <b>PVOID</b>.  

## -remarks
To access receive segment coalescing (RSC) counter  information that is associated with a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure, an NDIS driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies the <b>TcpRecvSegCoalesceInfo</b> information type which is in an <b>NDIS_RSC_NBL_INFO</b> union.



To access RSC  timestamp information that is associated with a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure, an NDIS driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies the <b>RscTcpTimestampDelta</b> information type which is a single <b>ULONG</b> value.

The <b>RscTcpTimestampDelta</b> information might be set for coalesced segments that are using the TCP timestamp option. <b>RscTcpTimestampDelta</b> information should contain the delta between the earliest and the latest TCP timestamp values in the sequence of coalesced segments. The miniport driver can provide a 16-bit value for <b>RscTcpTimestampDelta</b>.  

The <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure of a single coalesced unit (SCU) is not different from the standard <b>NET_BUFFER_LIST</b> structure that is indicated on the receive path without RSC. The SCU resembles an IP jumbogram packet that came from the wire. Therefore, every indicated SCU must have one <a href="netvista.net_buffer">NET_BUFFER</a> structure for each <b>NET_BUFFER_LIST</b>. 

The <a href="netvista.net_buffer">NET_BUFFER</a>  can be an MDL chain and the MDL can have a total size that exceeds the normal maximum transmission unit (MTU) but must be limited by the maximum legal IP datagram length, see RFC791 section 3.1.


Also, the additional <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> information can be provided for an SCU. 
NDIS performs the <b>NET_BUFFER_LIST</b> and <a href="netvista.net_buffer">NET_BUFFER</a> validation. The host TCPIP stack performs packet checks including IP and TCP header validation. 


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported for NDIS 6.30 and later drivers in Windows 8.
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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439944">NET_BUFFER_LIST_COALESCED_SEG_COUNT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439945">NET_BUFFER_LIST_DUP_ACK_COUNT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSC_NBL_INFO union%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
