---
UID: NC.usbcamdi.PFNUSBCAMD_SetIsoPipeState
title: PFNUSBCAMD_SetIsoPipeState
author: windows-driver-content
description: The USBCAMD_SetIsoPipeState service permits the camera minidriver to control the streaming state on the isochronous pipe.
old-location: stream\usbcamd_setisopipestate.htm
old-project: stream
ms.assetid: 6170c69d-f73d-4ba4-b7de-06257c8dd83c
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
req.alt-api: USBCAMD_SetIsoPipeState
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

# PFNUSBCAMD_SetIsoPipeState callback



## -description
The <b>USBCAMD_SetIsoPipeState</b> service permits the camera minidriver to control the streaming state on the isochronous pipe.



## -prototype

````
PFNUSBCAMD_SetIsoPipeState USBCAMD_SetIsoPipeState;

NTSTATUS APIENTRY USBCAMD_SetIsoPipeState(
  _In_ PVOID DeviceContext,
  _In_ ULONG PipeStateFlags
)
{ ... }
````


## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.


### -param PipeStateFlags [in]

Specifies the isochronous pipe state. This argument should be set to either of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_STOP_STREAM

</td>
<td>
This flags indicates to stop streaming.

</td>
</tr>
<tr>
<td>
USBCAMD_START_STREAM

</td>
<td>
This flags indicates to start streaming.

</td>
</tr>
</table>
 


## -returns
<b>USBCAMD_SetIsoPipeState</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The requested pipe state is the same as the current pipe state.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The pipe state change is deferred.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are insufficient resources to allocate a work item to change the pipe state.

 


## -remarks
Note that the streaming state on the isochronous pipe works differently from the streaming state in the stream class and in Microsoft DirectShow. It is possible to stop the isochronous pipe from streaming for a short period while the overall video capture graph is still in a Run state.

This function is used to enable dual-mode cameras. In a dual-mode camera, if there is a request to get still data while streaming is in progress, the stream must be stopped on the isochronous pipe. The still call is then serviced and then the isochronous stream must be restarted, all while the overall stream class/DirectShow graph is still in a <b>Run</b> state.

Using this function does not enable you to change the alternate setting within the USB video streaming interface or the channel bandwidth. The isochronous stream must be closed before the alternate setting is changed.

<b>USBCAMD_SetIsoPipeState</b> is not available in USBCAMD version 1.0.


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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_SetIsoPipeState routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

