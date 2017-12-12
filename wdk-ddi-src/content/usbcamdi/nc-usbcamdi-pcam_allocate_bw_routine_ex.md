---
UID: NC.usbcamdi.PCAM_ALLOCATE_BW_ROUTINE_EX
title: PCAM_ALLOCATE_BW_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamAllocateBandwidthEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camallocatebandwidthex.htm
old-project: stream
ms.assetid: 00d8385e-e339-4e63-a79a-f5fa87d8987d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CamAllocateBandwidthEx
req.alt-loc: usbcamdi.h
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
req.product: Windows 10 or later.
---

# PCAM_ALLOCATE_BW_ROUTINE_EX callback



## -description
A camera minidriver's <b>CamAllocateBandwidthEx</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.



## -prototype

````
PCAM_ALLOCATE_BW_ROUTINE_EX CamAllocateBandwidthEx;

NTSTATUS CamAllocateBandwidthEx(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext,
   PULONG         RawFrameLength,
   PVOID          Format,
   ULONG          StreamNumber
)
{ ... }
````


## -parameters

### -param BusDeviceObject 

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext 

Pointer to the camera minidriver's device context.


### -param RawFrameLength 

Specifies the size, in bytes, of the raw frame data from the packet stream.


### -param Format 

Pointer to a <a href="stream.ks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure associated with this stream.


### -param StreamNumber 

Specifies the stream number.


## -returns
<b>CamAllocateBandwidthEx</b> returns STATUS_SUCCESS or an appropriate error code.


## -remarks
USBCAMD calls the camera minidriver's <b>CamAllocateBandwidthEx</b> callback function immediately before the isochronous video capture stream is started. It is called in connection with a <b>Run</b> command.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

The original USBCAMD does not call <b>CamAllocateBandwidthEx</b>.

This function is required.


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
Header

</th>
<td width="70%">
<dl>
<dt>Usbcamdi.h (include Usbcamdi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>
</dt>
<dt>
<a href="stream.usbcamd_selectalternateinterface">USBCAMD_SelectAlternateInterface</a>
</dt>
<dt>
<a href="stream.ks_dataformat_videoinfoheader">KS_DATAFORMAT_VIDEOINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20CamAllocateBandwidthEx routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

