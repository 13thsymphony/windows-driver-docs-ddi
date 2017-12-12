---
UID: NC.usbcamdi.PCAM_NEW_FRAME_ROUTINE_EX
title: PCAM_NEW_FRAME_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamNewVideoFrameEx callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframeex.htm
old-project: stream
ms.assetid: 739e434e-9621-4927-bf1d-2e7c3b2828d7
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
req.alt-api: CamNewVideoFrameEx
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
req.irql: DISPATCH_LEVEL (See Remarks section)
req.product: Windows 10 or later.
---

# PCAM_NEW_FRAME_ROUTINE_EX callback



## -description
A camera minidriver's <b>CamNewVideoFrameEx</b> callback function initializes a new video frame context structure.



## -prototype

````
PCAM_NEW_FRAME_ROUTINE_EX CamNewVideoFrameEx;

VOID CamNewVideoFrameEx(
   PVOID  DeviceContext,
   PVOID  FrameContext,
   ULONG  StreamNumber,
   PULONG FrameLength
)
{ ... }
````


## -parameters

### -param DeviceContext 

Specifies the minidriver device context.


### -param FrameContext 

Specifies the frame context to be initialized.


### -param StreamNumber 

Indicates the stream associated with this new frame.


### -param FrameLength 

Pointer to the raw frame buffer length. The length is expressed in bytes. The camera minidriver may decrease this value if it does not require a buffer transfer on the USB bus of the specified size. The camera minidriver should not increase this value.


## -returns
<b>CamNewVideoFrameEx</b> does not return a value.


## -remarks
USBCAMD calls the camera minidriver's <b>CamNewVideoFrameEx</b> callback function at IRQL = DISPATCH_LEVEL.

The original USBCAMD does not call <b>CamNewVideoFrameEx</b>.

This function is optional.


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL (See Remarks section)

</td>
</tr>
</table>