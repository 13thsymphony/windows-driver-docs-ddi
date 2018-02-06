---
UID: NF:d3dkmthk.D3DKMTGetOverlayState
title: D3DKMTGetOverlayState function
author: windows-driver-content
description: The D3DKMTGetOverlayState function retrieves the status about an overlay.
old-location: display\d3dkmtgetoverlaystate.htm
old-project: display
ms.assetid: 6e3db876-c9f9-4de9-a0e2-5911132b72be
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTGetOverlayState, d3dkmthk/D3DKMTGetOverlayState, D3DKMTGetOverlayState function [Display Devices], OpenGL_Functions_f2301345-c6d8-42bf-82f9-f8f97d29674f.xml, display.d3dkmtgetoverlaystate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTGetOverlayState is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTGetOverlayState
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTGetOverlayState function
The <b>D3DKMTGetOverlayState</b> function retrieves the status about an overlay.

## Syntax

````
NTSTATUS D3DKMTGetOverlayState(
  _Inout_ D3DKMT_GETOVERLAYSTATE *pData
);
````

## Parameters

This function has no parameters.

## Return Value

<b>D3DKMTGetOverlayState</b> returns one of the following values:
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
The status about an overlay was successfully retrieved. 

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

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMTGetOverlayState is supported beginning with the Windows 7 operating system. D3DKMTGetOverlayState is supported beginning with the Windows 7 operating system. |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getoverlaystate.md">D3DKMT_GETOVERLAYSTATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetOverlayState function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>