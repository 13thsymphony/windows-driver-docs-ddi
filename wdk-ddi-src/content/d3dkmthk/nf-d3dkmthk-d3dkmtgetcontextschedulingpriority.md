---
UID: NF:d3dkmthk.D3DKMTGetContextSchedulingPriority
title: D3DKMTGetContextSchedulingPriority function
author: windows-driver-content
description: The D3DKMTGetContextSchedulingPriority function retrieves the scheduling priority for a device context.
old-location: display\d3dkmtgetcontextschedulingpriority.htm
old-project: display
ms.assetid: db4968d3-c23b-417f-9c91-552923dce1ea
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTGetContextSchedulingPriority function [Display Devices], OpenGL_Functions_2f186385-7f1b-445e-93f9-594dea4feeb4.xml, d3dkmthk/D3DKMTGetContextSchedulingPriority, display.d3dkmtgetcontextschedulingpriority, D3DKMTGetContextSchedulingPriority
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
-	D3DKMTGetContextSchedulingPriority
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTGetContextSchedulingPriority function
The <b>D3DKMTGetContextSchedulingPriority</b> function retrieves the scheduling priority for a device context.

## Syntax

````
NTSTATUS D3DKMTGetContextSchedulingPriority(
  _Inout_ D3DKMT_GETCONTEXTSCHEDULINGPRIORITY *pData
);
````

## Parameters

This function has no parameters.

## Return Value

<b>D3DKMTGetContextSchedulingPriority</b> returns one of the following values:

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
The scheduling priority was successfully retrieved.

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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getcontextschedulingpriority.md">D3DKMT_GETCONTEXTSCHEDULINGPRIORITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetContextSchedulingPriority function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>