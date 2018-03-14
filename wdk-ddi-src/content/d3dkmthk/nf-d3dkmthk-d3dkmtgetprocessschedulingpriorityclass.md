---
UID: NF:d3dkmthk.D3DKMTGetProcessSchedulingPriorityClass
title: D3DKMTGetProcessSchedulingPriorityClass function
author: windows-driver-content
description: The D3DKMTGetProcessSchedulingPriorityClass function retrieves the scheduling priority for a process.
old-location: display\d3dkmtgetprocessschedulingpriorityclass.htm
old-project: display
ms.assetid: 994df4be-d0ce-4f64-91f5-b5516ce947ec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTGetProcessSchedulingPriorityClass, D3DKMTGetProcessSchedulingPriorityClass function [Display Devices], OpenGL_Functions_7af39e72-516e-440a-b4be-f0b3f82156d0.xml, d3dkmthk/D3DKMTGetProcessSchedulingPriorityClass, display.d3dkmtgetprocessschedulingpriorityclass
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
-	D3DKMTGetProcessSchedulingPriorityClass
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTGetProcessSchedulingPriorityClass function
The <b>D3DKMTGetProcessSchedulingPriorityClass</b> function retrieves the scheduling priority for a process.

## Syntax

````
NTSTATUS D3DKMTGetProcessSchedulingPriorityClass(
  _In_  HANDLE                         hProcess,
  _Out_ D3DKMT_SCHEDULINGPRIORITYCLASS *pPriority
);
````

## Parameters

`Arg1`



`Arg1`




## Return Value

<b>D3DKMTGetProcessSchedulingPriorityClass</b> returns one of the following values:

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

<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md">D3DKMT_SCHEDULINGPRIORITYCLASS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetprocessschedulingpriorityclass.md">D3DKMTSetProcessSchedulingPriorityClass</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetProcessSchedulingPriorityClass function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>