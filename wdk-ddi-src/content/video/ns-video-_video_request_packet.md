---
UID: NS.VIDEO._VIDEO_REQUEST_PACKET
title: _VIDEO_REQUEST_PACKET
author: windows-driver-content
description: A pointer to a VIDEO_REQUEST_PACKET structure is passed to the miniport driver's HwVidStartIO function by the video port driver.
old-location: display\video_request_packet.htm
old-project: display
ms.assetid: 8ccc8c97-4c8c-4278-8eef-a612ce85439e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VIDEO_REQUEST_PACKET, VIDEO_REQUEST_PACKET, *PVIDEO_REQUEST_PACKET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_REQUEST_PACKET
req.alt-loc: video.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# _VIDEO_REQUEST_PACKET structure



## -description
A pointer to a VIDEO_REQUEST_PACKET structure is passed to the miniport driver's <a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a> function by the video port driver. The video port driver sets up the <a href="wdkgloss.v#wdkgloss.video_request_packet__vrp_#wdkgloss.video_request_packet__vrp_"><i>VRP</i></a> from the IRP code (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550710">IRP Major Function Codes</a>) sent in response to a GDI call to <a href="display.engdeviceiocontrol">EngDeviceIoControl</a>. Usually, the corresponding display driver makes the call to <b>EngDeviceIoControl</b> when it needs support from the video port-miniport driver pair. The video port driver calls the miniport driver with the <i>VRP</i> to process the given IOCTL_VIDEO_<i>XXX</i> request.


## -syntax

````
typedef struct _VIDEO_REQUEST_PACKET {
  ULONG         IoControlCode;
  PSTATUS_BLOCK StatusBlock;
  PVOID         InputBuffer;
  ULONG         InputBufferLength;
  PVOID         OutputBuffer;
  ULONG         OutputBufferLength;
} VIDEO_REQUEST_PACKET, *PVIDEO_REQUEST_PACKET;
````


## -struct-fields

### -field IoControlCode

Specifies an IOCTL_VIDEO_<i>XXX</i> value passed to the <b>EngDeviceIoControl</b> function by the caller and sent to the video port driver in an IRP code. For more information about the set of system-defined IOCTL_VIDEO_<i>XXX</i> that miniport drivers must support, see <a href="display.video_miniport_driver_i_o_control_codes">Video Miniport Driver I/O Control Codes</a>.

### -field StatusBlock

Pointer to a STATUS_BLOCK structure in the <a href="wdkgloss.v#wdkgloss.video_request_packet__vrp_#wdkgloss.video_request_packet__vrp_"><i>VRP</i></a>. <b>StatusBlock</b> is filled in by the miniport driver with return information upon completion of each VRP.

### -field InputBuffer

Pointer to an input buffer that contains information passed in by the caller. The structure for the data depends on the value of <b>IoControlCode</b>. This member actually points to the same buffer as that indicated by <b>OutputBuffer</b>.

### -field InputBufferLength

Specifies the size in bytes of the input buffer.

### -field OutputBuffer

Pointer to an output buffer into which the miniport driver transfers data to be returned to the caller. The structure for the data depends on the value of <b>IoControlCode.</b> Because this member points to the same buffer as <b>InputBuffer</b>, a miniport driver must not write output in the <b>OutputBuffer</b> before it has consumed all input data from the <b>InputBuffer</b>.

### -field OutputBufferLength

Specifies the size in bytes of the output buffer. A miniport driver cannot enlarge this buffer. A miniport driver should set the <b>Status</b> member of the <b>StatusBlock</b> with ERROR_INSUFFICIENT_BUFFER or ERROR_MORE_DATA if the given <b>OutputBuffer</b> is too small to contain all the returned information.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a>
</dt>
<dt>
<a href="display.video_miniport_driver_i_o_control_codes">Video Miniport Driver I/O Control Codes</a>
</dt>
<dt>
<a href="display.status_block">STATUS_BLOCK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_REQUEST_PACKET structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
