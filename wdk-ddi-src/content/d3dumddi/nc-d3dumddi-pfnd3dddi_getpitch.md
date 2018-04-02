---
UID: NC:d3dumddi.PFND3DDDI_GETPITCH
title: PFND3DDDI_GETPITCH
author: windows-driver-content
description: The GetPitch function retrieves the pitch of a protected or non-lockable surface.
old-location: display\getpitch.htm
old-project: display
ms.assetid: 1a5721a3-c03f-4827-9626-c9b6af5059a1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetPitch, GetPitch callback function [Display Devices], PFND3DDDI_GETPITCH, UserModeDisplayDriver_Functions_6a055fa5-1f52-4d88-af1b-e9cab4abef13.xml, d3dumddi/GetPitch, display.getpitch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetPitch is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	GetPitch
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_GETPITCH callback function
The <i>GetPitch</i> function retrieves the pitch of a protected or non-lockable surface.

## Syntax

```
PFND3DDDI_GETPITCH Pfnd3dddiGetpitch;

HRESULT Pfnd3dddiGetpitch(
  HANDLE hDevice,
  D3DDDIARG_GETPITCH *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

The <i>GetPitch</i> function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The pitch of the protected surface is successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the <i>GetPitch</i> function. 

</td>
</tr>
</table>

## Remarks

Hardware and drivers can optionally support the <i>GetPitch</i> function.  

The surface for which the <i>GetPitch</i> function returns the pitch can be non-lockable or protected. Therefore, the application cannot retrieve the pitch of the surface through a call to the driver's <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function. The application must retrieve the pitch of the surface to properly allocate the system memory buffer that the application subsequently uses in calls to the driver's <a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a> and <a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | GetPitch is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543176">D3DDDIARG_GETPITCH</a>



<a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a>



<a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a>