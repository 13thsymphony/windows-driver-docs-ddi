---
UID: NC:hidclass.PHIDP_GETCAPS
title: PHIDP_GETCAPS
author: windows-driver-content
description: The HidP_GetCaps routine returns a top-level collection's HIDP_CAPS structure.
old-location: hid\hidp_getcaps.htm
old-project: hid
ms.assetid: a43baab5-26d9-43f7-bc13-3b0864769e68
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidP_GetCaps, HidP_GetCaps callback function [Human Input Devices], PHIDP_GETCAPS, hid.hidp_getcaps, hidfunc_420188e5-e357-43cc-b195-dea7637fd3c9.xml, hidpi/HidP_GetCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	hidpi.h
api_name:
-	HidP_GetCaps
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---


# PHIDP_GETCAPS callback function
The <b>HidP_GetCaps</b> routine returns a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

## Syntax

```
PHIDP_GETCAPS PhidpGetcaps;

NTSTATUS PhidpGetcaps(
  PHIDP_PREPARSED_DATA PreparsedData,
  PHIDP_CAPS Capabilities
)
{...}
```

## Parameters

`PreparsedData`

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

`Capabilities`

Pointer to a caller-allocated buffer that the routine uses to return a collection's HIDP_CAPS structure.


## Return Value

<b>HidP_GetCaps</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the collection capability information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The specified preparsed data is invalid.

</td>
</tr>
</table>

## Remarks

For more information about a collection's capability, see <a href="https://msdn.microsoft.com/0568993b-ff50-48ac-a875-95ab643d6c28">Obtaining Collection Information</a>.

See also <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | hidclass.h (include Hidclass.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_descriptor.md">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a>



<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a>