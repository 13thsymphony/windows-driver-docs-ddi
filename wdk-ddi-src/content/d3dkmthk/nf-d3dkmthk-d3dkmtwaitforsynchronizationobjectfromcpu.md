---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromCpu
title: D3DKMTWaitForSynchronizationObjectFromCpu function
author: windows-driver-content
description: D3DKMTWaitForSynchronizationObjectFromCpu waits for a monitored fence to reach a certain value.
old-location: display\d3dkmtwaitforsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: C65880F7-DFCA-4DF9-ABF1-95A82D1D43ED
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTWaitForSynchronizationObjectFromCpu, D3DKMTWaitForSynchronizationObjectFromCpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromCpu, display.d3dkmtwaitforsynchronizationobjectfromcpu
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTWaitForSynchronizationObjectFromCpu
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTWaitForSynchronizationObjectFromCpu function
<b>D3DKMTWaitForSynchronizationObjectFromCpu</b> waits for a monitored fence to reach a certain value.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTWaitForSynchronizationObjectFromCpu(
  _In_ const D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU *pData
);
````

## Parameters

`D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU`

TBD


## Return Value

Returns one of the following values:

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
The operation was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
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
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu.md">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</a>