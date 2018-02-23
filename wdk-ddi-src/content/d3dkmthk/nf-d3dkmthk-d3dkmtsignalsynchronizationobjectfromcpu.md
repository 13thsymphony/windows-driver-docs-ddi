---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromCpu
title: D3DKMTSignalSynchronizationObjectFromCpu function
author: windows-driver-content
description: D3DKMTSignalSynchronizationObjectFromCpu enables a driver to signal a monitored fence.D3DKMTSignalSynchronizationObjectFromCpu enables a driver to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 23DC5EB1-E606-499D-B78A-AFF95E6B00A3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3dkmtsignalsynchronizationobjectfromcpu, D3DKMTSignalSynchronizationObjectFromCpu, d3dkmthk/D3DKMTSignalSynchronizationObjectFromCpu, D3DKMTSignalSynchronizationObjectFromCpu function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTSignalSynchronizationObjectFromCpu
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSignalSynchronizationObjectFromCpu function
<b>D3DKMTSignalSynchronizationObjectFromCpu</b> enables a driver to signal a monitored fence.

## Syntax

````
HRESULT APIENTRY D3DKMTSignalSynchronizationObjectFromCpu(
  _In_ const D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *pData
);
````

## Parameters

`D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU`

TBD


## Return Value

<b>D3DKMTSignalSynchronizationObjectFromCpu</b> returns one of the following values:

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
The operation was successful.

</td>
</tr>
</table>
 

This function might also return other values.

## Remarks

When a monitored fence object is signaled by the CPU, the graphics kernel will update the fence memory location with the signaled value, so it becomes immediately visible to any user mode reader as well as immediately un-wait any satisfied waiters.
However, the caller cannot assume that the signal operation will be completed upon the return from this function. Instead, the caller should use appropriate Wait functions to check for signal completion.


<div class="alert"><b>Note</b>  A signal from a graphics processing unit (GPU) call is not provided. Instead, a driver can signal a new fence value by inserting a GPU write command for <b>FenceValueGPUVirtualAddress</b> into a command buffer.
</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |