---
UID: NC:usbcamdi.PFNUSBCAMD_CancelBulkReadWrite
title: PFNUSBCAMD_CancelBulkReadWrite
author: windows-driver-content
description: The USBCAMD_CancelBulkReadWrite service cancels a pending bulk read or write request.
old-location: stream\usbcamd_cancelbulkreadwrite.htm
old-project: stream
ms.assetid: e63a56d8-fdd8-468d-b0f9-2c46c5ff7a00
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PFNUSBCAMD_CancelBulkReadWrite, USBCAMD_CancelBulkReadWrite, USBCAMD_CancelBulkReadWrite routine [Streaming Media Devices], stream.usbcamd_cancelbulkreadwrite, usbcamdi/USBCAMD_CancelBulkReadWrite, usbcmdpr_ba242b77-cda6-4b16-a7a1-297701108cd8.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	USBCAMD_CancelBulkReadWrite
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PFNUSBCAMD_CancelBulkReadWrite callback function
The <b>USBCAMD_CancelBulkReadWrite</b> service cancels a pending bulk read or write request.

## Syntax

```
PFNUSBCAMD_CancelBulkReadWrite PfnusbcamdCancelbulkreadwrite;

NTSTATUS PfnusbcamdCancelbulkreadwrite(
  PVOID DeviceContext,
  ULONG PipeIndex
)
{...}
```

## Parameters

`DeviceContext`

Pointer to device-specific context.

`PipeIndex`

Specifies the index of the bulk pipe to cancel the read or write request.


## Return Value

<b>USBCAMD_CancelBulkReadWrite</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

The value passed in the <i>PipeIndex</i> argument is invalid.

The type of the pipe specified by the <i>PipeIndex</i> argument represents an invalid type of pipe.

The current IRQL &gt;= DISPATCH_LEVEL.

</td>
</tr>
</table>

## Remarks

<b>USBCAMD_CancelBulkReadWrite</b> is not available in USBCAMD version 1.0.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568605">USBCAMD_INTERFACE</a>