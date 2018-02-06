---
UID: NS:strmini._HW_STREAM_REQUEST_BLOCK
title: "_HW_STREAM_REQUEST_BLOCK"
author: windows-driver-content
description: The stream class driver uses the HW_STREAM_REQUEST_BLOCK structure to pass information to and from the minidriver, using minidriver provided callbacks.
old-location: stream\hw_stream_request_block.htm
old-project: stream
ms.assetid: e2a19bb1-631d-4160-9980-f3cbeb0b085a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: strmini/HW_STREAM_REQUEST_BLOCK, strmini/PHW_STREAM_REQUEST_BLOCK, PHW_STREAM_REQUEST_BLOCK structure pointer [Streaming Media Devices], HW_STREAM_REQUEST_BLOCK, _HW_STREAM_REQUEST_BLOCK, PHW_STREAM_REQUEST_BLOCK, strclass-struct_4b0da124-b08a-49fe-acbc-9457db500b26.xml, *PHW_STREAM_REQUEST_BLOCK, HW_STREAM_REQUEST_BLOCK structure [Streaming Media Devices], stream.hw_stream_request_block
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	strmini.h
apiname:
-	HW_STREAM_REQUEST_BLOCK
product: Windows
targetos: Windows
req.typenames: "*PHW_STREAM_REQUEST_BLOCK, HW_STREAM_REQUEST_BLOCK"
req.product: Windows 10 or later.
---

# _HW_STREAM_REQUEST_BLOCK structure
The stream class driver uses the HW_STREAM_REQUEST_BLOCK structure to pass information to and from the minidriver, using minidriver provided callbacks.

## Syntax
````
typedef struct _HW_STREAM_REQUEST_BLOCK {
  ULONG                           SizeOfThisPacket;
  SRB_COMMAND                     Command;
  NTSTATUS                        Status;
  PHW_STREAM_OBJECT               StreamObject;
  PVOID                           HwDeviceExtension;
  PVOID                           SRBExtension;
  union {
    PKSSTREAM_HEADER                       DataBufferArray;
    PHW_STREAM_DESCRIPTOR                  StreamBuffer;
    KSSTATE                                StreamState;
    PSTREAM_TIME_REFERENCE                 TimeReference;
    PSTREAM_PROPERTY_DESCRIPTOR            PropertyInfo;
    PKSDATAFORMAT                          OpenFormat;
    struct _PORT_CONFIGURATION_INFORMATION  *ConfigInfo;
    HANDLE                                 MasterClockHandle;
    DEVICE_POWER_STATE                     DeviceState;
    PSTREAM_DATA_INTERSECT_INFO            IntersectInfo;
    PVOID                                  MethodInfo;
    LONG                                   FilterTypeIndex;
    BOOLEAN                                Idle;
  } CommandData;
  ULONG                           NumberOfBuffers;
  ULONG                           TimeoutCounter;
  ULONG                           TimeoutOriginal;
  struct _HW_STREAM_REQUEST_BLOCK  *NextSRB;
  PIRP                            Irp;
  ULONG                           Flags;
  PVOID                           HwInstanceExtension;
  union {
    ULONG NumberOfBytesToTransfer;
    ULONG ActualBytesTransferred;
  };
  PKSSCATTER_GATHER               ScatterGatherBuffer;
  ULONG                           NumberOfPhysicalPages;
  ULONG                           NumberOfScatterGatherElements;
  ULONG                           Reserved[1];
} HW_STREAM_REQUEST_BLOCK, *PHW_STREAM_REQUEST_BLOCK;
````

## Members


`_CommandData`

<b>CommandData</b> is a union of members provided for command-code-specific data.

`_HW_STREAM_REQUEST_BLOCK`



`Command`

Specifies the operation to be performed by the minidriver's callback. The class driver passes SRB_XXX command codes to minidriver callbacks.

`CommandData`

<b>CommandData</b> is a union of members provided for command-code-specific data.

`Flags`

Specifies the type of request. The class driver and the minidriver can use this member to determine which callback the class driver passed this stream request block to.
<table>
<tr>
<th>Value</th>
<th>Callback used</th>
</tr>
<tr>
<td>
None

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a>


</td>
</tr>
<tr>
<td>
SRB_HW_FLAGS_STREAM_REQUEST

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a>


</td>
</tr>
<tr>
<td>
SRB_HW_FLAGS_DATA_TRANSFER | SRB_HW_FLAGS_STREAM_REQUEST

</td>
<td>

<a href="..\strmini\nc-strmini-phw_receive_device_srb.md">StrMiniReceiveStreamDataPacket</a>


</td>
</tr>
</table> 

SRB_HW_FLAGS_STREAM_REQUEST bit is set for stream-specific requests (which are passed to the minidriver's <b>StrMiniReceiveStream</b><i>Xxx</i><b>Packet</b> routines). The SRB_HW_FLAGS_DATA_TRANSFER bit is set for data transfer requests (which are passed to the minidriver's

`HwDeviceExtension`

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information. The minidriver sets the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.

`HwInstanceExtension`

Pointer to the minidriver's instance extension. The minidriver may use this buffer to record private information global to this instance of the minidriver. The minidriver sets the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.

`Irp`

Pointer to the IRP for the request. Most minidrivers do not need to use this member.

`NextSRB`

Points to another stream request block. The minidriver can use this member to queue stream request blocks.

`NumberOfBuffers`

If Command is either <a href="https://msdn.microsoft.com/library/windows/hardware/ff568200">SRB_READ_DATA</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff568220">SRB_WRITE_DATA</a>, then this specifies the number of entries in the array of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structures that begins at the address pointed to by <b>CommandData.DataBufferArray</b>. Otherwise this parameter is unused.

`NumberOfPhysicalPages`

Specifies the size of the array passed in the <b>ScatterGatherBuffer</b> member.

`NumberOfScatterGatherElements`

Specifies the number of physical elements pointed to by <b>ScatterGatherBuffer</b>.

`Reserved`



`ScatterGatherBuffer`

Points to an array of KSSCATTER_GATHER structures, of the form:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct {
    PHYSICAL_ADDRESS PhysicalAddress;
    ULONG Length;
} KSSCATTER_GATHER, *PKSSCATTER_GATHER;</pre>
</td>
</tr>
</table></span></div>The array describes a scatter/gather list that can be used by the minidriver to do DMA. The memory does not need to be probed, locked, mapped, or flushed -- the stream class driver performs these for the minidriver.

`SizeOfThisPacket`

Specifies the size, in bytes, of this structure.

`SRBExtension`

Points to an uninitialized buffer the class driver allocates for the minidriver to use while processing this stream request block. This buffer is deallocated once the minidriver completes its handling of the block (see <a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a> or <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a> for details).

`Status`

When the minidriver completes a stream request, it fills this member with the status code of the request. See the documentation for the appropriate <b>StrMini</b><i>Xxx</i><b>Request</b> routine for the status codes minidrivers are expected to use.

`StreamObject`

For stream oriented requests, the class driver sets this to point to the <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a> structure that specifies the stream the class driver is making a request on.

`TimeoutCounter`

The number of seconds before this request times out. The class driver decrements this once per second. If the class driver decrements <b>TimeoutCounter</b> to zero before the minidriver completes this request, it will call the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568473">StrMiniRequestTimeout</a> routine. If the minidriver sets this to zero, the request does not time out.

`TimeoutOriginal`

The class driver sets this to the original value of <b>TimeoutCounter</b> upon the creation of the SRB.

## Remarks
The stream class driver passes pointers to HW_STREAM_REQUEST_BLOCK structures to the minidriver's <a href="..\strmini\nc-strmini-phw_receive_device_srb.md">StrMiniReceiveStreamDataPacket</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routines.

The minidriver owns this stream request block until the request times out or it completes the request. The minidriver signals to the class driver that it has completed the request by calling <a href="..\strmini\nf-strmini-streamclassdevicenotification.md">StreamClassDeviceNotification</a>(DeviceRequestComplete, pSrb-&gt;HwDeviceExtension, pSRB) for device-specific requests, or calling <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a>(StreamRequestComplete, pSrb-&gt;StreamObject, pSrb) for stream-specific requests. (The minidriver can also complete a request by calling <a href="..\strmini\nf-strmini-streamclasscompleterequestandmarkqueueready.md">StreamClassCompleteRequestAndMarkQueueReady</a>(pSrb). See that routine for details.)

If the class driver times out the request, it will call the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568473">StrMiniRequestTimeout</a> routine, which has the responsibility of terminating processing of the request. If the minidriver queues a request for later processing, it should set the <b>TimeoutCounter</b> member to zero, which will prevent the class driver from timing out the request. Once the minidriver is ready to resume processing the request, it should reset the <b>TimeoutCounter</b> member to the value of <b>TimeoutOriginal</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | strmini.h (include Strmini.h) |