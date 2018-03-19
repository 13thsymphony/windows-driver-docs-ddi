---
UID: NC:usbcamdi.PFNUSBCAMD_BulkReadWrite
title: PFNUSBCAMD_BulkReadWrite
author: windows-driver-content
description: The USBCAMD_BulkReadWrite service performs a read or write operation on the specified bulk pipe.
old-location: stream\usbcamd_bulkreadwrite.htm
old-project: stream
ms.assetid: 4888e6a7-be44-4ed9-80be-9dd7641653ef
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PFNUSBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite routine [Streaming Media Devices], stream.usbcamd_bulkreadwrite, usbcamdi/USBCAMD_BulkReadWrite, usbcmdpr_6044cfed-1a8c-48a5-ac28-16c8ac151fcc.xml
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	USBCAMD_BulkReadWrite
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PFNUSBCAMD_BulkReadWrite callback function
The <b>USBCAMD_BulkReadWrite</b> service performs a read or write operation on the specified bulk pipe.

## Syntax

```
PFNUSBCAMD_BulkReadWrite PfnusbcamdBulkreadwrite;

NTSTATUS PfnusbcamdBulkreadwrite(
  PVOID DeviceContext,
  USHORT PipeIndex,
  PVOID Buffer,
  ULONG BufferLength,
  PCOMMAND_COMPLETE_FUNCTION CommandComplete,
  PVOID CommandContext
)
{...}
```

## Parameters

`DeviceContext`

Pointer to the camera minidriver's device context.

`PipeIndex`

Specifies the index of the bulk pipe.

`Buffer`

Pointer to the read or write buffer. If this parameter is set to <b>NULL</b> for a read request, USBCAMD pulls a data SRB from the SRB read queue of the stream associated with this pipe. Write requests with a <b>NULL</b> buffer pointer are only permitted on the still pin if an SRB_WRITE_DATA request has been submitted to the still pin.

`BufferLength`

Specifies the length of the read/write buffer in bytes.

`CommandComplete`

Pointer to a camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>, which is called when the bulk read or write is completed. This value can be <b>NULL</b>.

`CommandContext`

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>.


## Return Value

<b>USBCAMD_BulkReadWrite</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
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

A bulk read/write request already exists.

The <i>Buffer</i> argument is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to schedule a transfer.

</td>
</tr>
</table>

## Remarks

USBCAMD can accept one read and one write request at a time.

<b>USBCAMD_BulkReadWrite</b> is not available in USBCAMD version 1.0.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>



<a href="..\usbcamdi\ns-usbcamdi-usbcamd_interface.md">USBCAMD_INTERFACE</a>