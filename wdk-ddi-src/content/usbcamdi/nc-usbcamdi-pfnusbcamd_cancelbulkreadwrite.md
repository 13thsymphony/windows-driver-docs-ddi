---
UID: NC.usbcamdi.PFNUSBCAMD_CancelBulkReadWrite
title: PFNUSBCAMD_CancelBulkReadWrite
author: windows-driver-content
description: The USBCAMD_CancelBulkReadWrite service cancels a pending bulk read or write request.
old-location: stream\usbcamd_cancelbulkreadwrite.htm
old-project: stream
ms.assetid: e63a56d8-fdd8-468d-b0f9-2c46c5ff7a00
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
req.alt-api: USBCAMD_CancelBulkReadWrite
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# PFNUSBCAMD_CancelBulkReadWrite callback



## -description
The <b>USBCAMD_CancelBulkReadWrite</b> service cancels a pending bulk read or write request.


## -prototype

````
PFNUSBCAMD_CancelBulkReadWrite USBCAMD_CancelBulkReadWrite;

NTSTATUS APIENTRY USBCAMD_CancelBulkReadWrite(
  _In_ PVOID DeviceContext,
  _In_ ULONG PipeIndex
)
{ ... }
````


## -parameters

### -param DeviceContext [in]

Pointer to device-specific context.

### -param PipeIndex [in]

Specifies the index of the bulk pipe to cancel the read or write request.

## -returns
<b>USBCAMD_CancelBulkReadWrite</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

The value passed in the <i>PipeIndex</i> argument is invalid.

The type of the pipe specified by the <i>PipeIndex</i> argument represents an invalid type of pipe.

The current IRQL &gt;= DISPATCH_LEVEL.

 

## -remarks
<b>USBCAMD_CancelBulkReadWrite</b> is not available in USBCAMD version 1.0.

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
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.usbcamd_interface">USBCAMD_INTERFACE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_CancelBulkReadWrite routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
