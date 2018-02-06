---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject
title: D3DKMTWaitForSynchronizationObject function
author: windows-driver-content
description: The D3DKMTWaitForSynchronizationObject function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject.htm
old-project: display
ms.assetid: 6b622b61-ec39-4ffb-b744-2b33ac560af6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTWaitForSynchronizationObject, OpenGL_Functions_bdec46cd-1e3b-427f-8c65-df2d31171bc5.xml, D3DKMTWaitForSynchronizationObject function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObject, display.d3dkmtwaitforsynchronizationobject
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
-	D3DKMTWaitForSynchronizationObject
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTWaitForSynchronizationObject function
The <b>D3DKMTWaitForSynchronizationObject</b> function inserts a wait for the specified synchronization objects in the specified context stream.

## Syntax

````
NTSTATUS D3DKMTWaitForSynchronizationObject(
  _In_ const D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *pData
);
````

## Parameters

`D3DKMT_WAITFORSYNCHRONIZATIONOBJECT`

TBD


## Return Value

<b>D3DKMTWaitForSynchronizationObject</b> returns one of the following values:
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
The wait was successfully set up.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTWaitForSynchronizationObject function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>