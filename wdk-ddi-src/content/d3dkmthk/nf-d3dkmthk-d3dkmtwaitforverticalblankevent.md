---
UID: NF:d3dkmthk.D3DKMTWaitForVerticalBlankEvent
title: D3DKMTWaitForVerticalBlankEvent function
author: windows-driver-content
description: The D3DKMTWaitForVerticalBlankEvent function waits for the vertical blanking interval to occur and then returns.
old-location: display\d3dkmtwaitforverticalblankevent.htm
old-project: display
ms.assetid: aa40633e-1881-4bf4-a57b-f7ee3ce23438
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTWaitForVerticalBlankEvent, D3DKMTWaitForVerticalBlankEvent function [Display Devices], OpenGL_Functions_9e2c6684-7429-43d7-b43a-0f11aea6807f.xml, d3dkmthk/D3DKMTWaitForVerticalBlankEvent, display.d3dkmtwaitforverticalblankevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTWaitForVerticalBlankEvent
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTWaitForVerticalBlankEvent function
The <b>D3DKMTWaitForVerticalBlankEvent</b> function waits for the vertical blanking interval to occur and then returns.

## Syntax

```
NTSTATUS D3DKMTWaitForVerticalBlankEvent(
  CONST *D3DKMT_WAITFORVERTICALBLANKEVENT
);
```

## Parameters

`D3DKMT_WAITFORVERTICALBLANKEVENT`

TBD


## Return Value

<b>D3DKMTWaitForVerticalBlankEvent</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The vertical blanking interval successfully occurred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548441">D3DKMT_WAITFORVERTICALBLANKEVENT</a>