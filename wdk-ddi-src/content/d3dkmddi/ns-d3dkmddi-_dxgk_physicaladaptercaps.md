---
UID: NS.D3DKMDDI._DXGK_PHYSICALADAPTERCAPS
title: _DXGK_PHYSICALADAPTERCAPS
author: windows-driver-content
description: The DXGK_PHYSICALADAPTERCAPS structure is used to report details of a physical adapter.
old-location: display\dxgk_physicaladaptercaps.htm
old-project: display
ms.assetid: 8D075473-605F-4B75-BB02-5B182EEB3B5F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_PHYSICALADAPTERCAPS, DXGK_PHYSICALADAPTERCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_PHYSICALADAPTERCAPS
req.alt-loc: d3dkmddi.h
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
---

# _DXGK_PHYSICALADAPTERCAPS structure



## -description
The <b>DXGK_PHYSICALADAPTERCAPS</b> structure is used to report details of a physical adapter.


## -syntax

````
typedef struct _DXGK_PHYSICALADAPTERCAPS {
  WORD                      NumExecutionNodes;
  WORD                      PagingNodeIndex;
  HANDLE                    DxgkPhysicalAdapterHandle;
  DXGK_PHYSICALADAPTERFLAGS Flags;
  UINT                      VPRPagingNode;
} DXGK_PHYSICALADAPTERCAPS;
````


## -struct-fields

### -field NumExecutionNodes

The number of execution nodes in the physical adapter.

### -field PagingNodeIndex

Index of the paging node for the physical adapter.

### -field DxgkPhysicalAdapterHandle

Handle, which is passed to the kernel mode driver as <b>DXGKRNL_INTERFACE::DeviceHandle</b> in <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>. 

### -field Flags

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field Flags.IoMmuSupported
### -field TRUE

</td>
<td width="60%">
The adapter supports <i>IoMmu</i>.
</td>
</tr>
<tr>

### -field Flags.GpuMmuSupported
### -field TRUE

</td>
<td width="60%">
The adapter supports <i>GpuMmu</i>.
</td>
</tr>
<tr>

### -field Flags.MovePagingSupported
### -field TRUE

</td>
<td width="60%">
The adapter supports move paging.
</td>
</tr>
<tr>

### -field Flags.VPRPagingContextRequired
### -field TRUE

</td>
<td width="60%">
The adapter requires the index of the VPR paging node.
</td>
</tr>
</table>
 

### -field VPRPagingNode

Index of the node to be used for move paging in  the VPR.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>