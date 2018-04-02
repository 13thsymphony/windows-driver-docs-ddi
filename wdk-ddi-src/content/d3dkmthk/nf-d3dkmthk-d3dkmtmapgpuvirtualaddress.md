---
UID: NF:d3dkmthk.D3DKMTMapGpuVirtualAddress
title: D3DKMTMapGpuVirtualAddress function
author: windows-driver-content
description: D3DKMTMapGpuVirtualAddress maps a graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.
old-location: display\d3dkmtmapgpuvirtualaddress.htm
old-project: display
ms.assetid: 6CE8112F-1DDA-4A8B-8D3D-40DC3737976A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTMapGpuVirtualAddress, D3DKMTMapGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTMapGpuVirtualAddress, display.d3dkmtmapgpuvirtualaddress
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
-	D3DKMTMapGpuVirtualAddress
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTMapGpuVirtualAddress function
<b>D3DKMTMapGpuVirtualAddress</b> maps a graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state. The driver can specify a base GPU virtual address to map or let the video memory manager automatically pick one. 
When specifying a non-NULL base address, the entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> must be in a freed state or belong to a virtual address range that was obtained by calling <b>MapGpuVirtualAddress</b> or <a href="https://msdn.microsoft.com/26A827F1-1094-4A7D-9C63-758925EE6273">DxgkCbReserveGpuVirtualAddressRange</a>. Note that when <b>Protection.Zero</b> or <b>Protection.NoAccess</b> is specified, the virtual address range cannot belong to a range that was obtained by calling <b>MapGpuVirtualAddress</b>.
The driver may specify if the mapping should allow for write and execute privileges in addition to read privileges, which always exist by default. 
In the  linked display adapter configuration the paging queue defines a physical GPU, whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.

## Syntax

```
NTSTATUS D3DKMTMapGpuVirtualAddress(

);
```

## Parameters

This function has no parameters.

## Return Value

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
The device context was successfully created.

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
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |

## See Also

<a href="https://msdn.microsoft.com/26A827F1-1094-4A7D-9C63-758925EE6273">DxgkCbReserveGpuVirtualAddressRange</a>