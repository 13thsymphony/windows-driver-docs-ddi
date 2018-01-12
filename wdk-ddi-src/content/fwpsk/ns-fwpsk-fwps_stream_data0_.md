---
UID: NS:fwpsk.FWPS_STREAM_DATA0_
title: FWPS_STREAM_DATA0_
author: windows-driver-content
description: The FWPS_STREAM_DATA0 structure describes a portion of a data stream.Note  FWPS_STREAM_DATA0 is a specific version of FWPS_STREAM_DATA.
old-location: netvista\fwps_stream_data0.htm
old-project: netvista
ms.assetid: 7e9daf20-12d6-42dc-99fb-9e9efe5a9900
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FWPS_STREAM_DATA0_, FWPS_STREAM_DATA0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_STREAM_DATA0
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
req.typenames: FWPS_STREAM_DATA0
---

# FWPS_STREAM_DATA0_ structure



## -description
The <b>FWPS_STREAM_DATA0</b> structure describes a portion of a data stream.



## -syntax

````
typedef struct FWPS_STREAM_DATA0_ {
  UINT32                   flags;
  FWPS_STREAM_DATA_OFFSET0 dataOffset;
  SIZE_T                   dataLength;
  NET_BUFFER_LIST          *netBufferListChain;
} FWPS_STREAM_DATA0;
````


## -struct-fields

### -field flags

A variable containing flags that specify the characteristics of the data stream.
     

For inbound data streams, this can be one or more of the following flags:




### -field FWPS_STREAM_FLAG_RECEIVE

Specifies that the stream is an inbound data stream. This flag is always set for inbound data
       streams.


### -field FWPS_STREAM_FLAG_RECEIVE_EXPEDITED

Specifies that the inbound data stream contains high-priority out-of-band data.


### -field FWPS_STREAM_FLAG_RECEIVE_DISCONNECT

Specifies that the inbound data has arrived with the FIN flag set in the TCP header. This
       indicates that the sender has disconnected the stream.


### -field FWPS_STREAM_FLAG_RECEIVE_ABORT

Specifies that the inbound data has arrived with the RST flag set in the TCP header. This
       indicates that the sender has reset the stream.
       

<div class="alert"><b>Note</b>  This flag is not implemented in Windows Vista.</div>
<div> </div>
</dd>
</dl>
For outbound data streams, this can be one or more of the following flags:




### -field FWPS_STREAM_FLAG_SEND

Specifies that the stream is an outbound data stream. This flag is always set for outbound data
       streams.


### -field FWPS_STREAM_FLAG_SEND_EXPEDITED

Specifies that the outbound data stream contains high-priority out-of-band data.


### -field FWPS_STREAM_FLAG_SEND_NODELAY

Specifies that the sending client requests that the outbound data stream is not to be buffered.
       If this flag is set, a callout driver should not hold onto the stream buffer any longer than
       necessary.


### -field FWPS_STREAM_FLAG_SEND_DISCONNECT

Specifies that the stream is to be disconnected after the data in the outbound data stream has
       been sent. The network stack will set the FIN flag in the TCP header of the last packet that is sent
       out.


### -field FWPS_STREAM_FLAG_SEND_ABORT

Specifies that the stream is to be reset after the data in the outbound data stream has been
       sent. The network stack will set the RST flag in the TCP header of the last packet that is sent out.
       Callout drivers must not call the 
       <a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a> function
       to inject data into the stream if this flag is set.
       

<div class="alert"><b>Note</b>  This flag is not implemented in Windows Vista.</div>
<div> </div>
</dd>
</dl>

### -field dataOffset

An 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_data_offset0_.md">FWPS_STREAM_DATA_OFFSET0</a> structure
     that specifies the offset into the data stream where the portion of the data stream begins.


### -field dataLength

The number of bytes in the portion of the data stream.


### -field netBufferListChain

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the portion of the data stream.


## -remarks
The filter engine uses the FWPS_STREAM_DATA0 structure to describe the portion of a data stream that a
    callout's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function can process. The 
    <b>dataStream</b> member of the 
    <a href="..\fwpsk\ns-fwpsk-fwps_stream_callout_io_packet0_.md">
    FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure points to an FWPS_STREAM_DATA0 structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

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
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_stream_callout_io_packet0_.md">
   FWPS_STREAM_CALLOUT_IO_PACKET0</a>
</dt>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_stream_data_offset0_.md">FWPS_STREAM_DATA_OFFSET0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_STREAM_DATA0 structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

