---
UID: NC.usbcamdi.PFNUSBCAMD_SetVideoFormat
title: PFNUSBCAMD_SetVideoFormat
author: windows-driver-content
description: The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed.
old-location: stream\usbcamd_setvideoformat.htm
old-project: stream
ms.assetid: 84a63c69-0f27-42e4-ae10-e394dd8b715d
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
req.alt-api: USBCAMD_SetVideoFormat
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

# PFNUSBCAMD_SetVideoFormat callback



## -description
The <b>USBCAMD_SetVideoFormat</b> service is used to notify USBCAMD that the video format has changed.


## -prototype

````
PFNUSBCAMD_SetVideoFormat USBCAMD_SetVideoFormat;

NTSTATUS APIENTRY USBCAMD_SetVideoFormat(
  _In_ PVOID                    DeviceContext,
  _In_ PHW_STREAM_REQUEST_BLOCK pSrb
)
{ ... }
````


## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param pSrb [in]

Pointer to a stream request block (SRB).

## -returns
<b>USBCAMD_SetVideoFormat</b> returns <b>TRUE</b> if the call was successful, otherwise it returns <b>FALSE</b> and sets <i>pSrb-&gt;Status</i> to one of the following error codes:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

Unknown video format

Arithmetic overflow when calculating the video info header size or format size.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are insufficient resources to allocate the video info header.

 

## -remarks
Note that this function returns <b>TRUE</b> to indicate success and not STATUS_SUCCESS.

Camera minidrivers must handle all SRBs related to video format. Camera minidrivers should use <b>USBCAMD_SetVideoFormat</b> to inform USBCAMD of a video format change. Typically, the camera minidriver calls <b>USBCAMD_SetVideoFormat</b> from within its SRB_SET_DATA_FORMAT handler.

<b>USBCAMD_SetVideoFormat</b> is not available in USBCAMD version 1.0.

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
<a href="stream.usbcamd_interface">USBCAMD_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568201">SRB_SET_DATA_FORMAT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_SetVideoFormat routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
