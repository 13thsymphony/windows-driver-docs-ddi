---
UID: NS:d3dkmddi._DXGKARG_QUERYDEPENDENTENGINEGROUP
title: "_DXGKARG_QUERYDEPENDENTENGINEGROUP"
author: windows-driver-content
description: Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the DxgkDdiQueryDependentEngineGroup function to query node dependencies.
old-location: display\dxgkarg_querydependentenginegroup.htm
old-project: display
ms.assetid: 6b1d6465-83bd-42c4-be1f-d7a2cfb74483
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*INOUT_DXGKARG_QUERYDEPENDENTENGINEGROUP, DXGKARG_QUERYDEPENDENTENGINEGROUP, DXGKARG_QUERYDEPENDENTENGINEGROUP structure [Display Devices], _DXGKARG_QUERYDEPENDENTENGINEGROUP, d3dkmddi/DXGKARG_QUERYDEPENDENTENGINEGROUP, display.dxgkarg_querydependentenginegroup"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARG_QUERYDEPENDENTENGINEGROUP
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYDEPENDENTENGINEGROUP
---

# _DXGKARG_QUERYDEPENDENTENGINEGROUP structure
Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the <a href="https://msdn.microsoft.com/42040ffc-40a3-4794-805c-7a165c47c8c9">DxgkDdiQueryDependentEngineGroup</a> function to query node dependencies.

## Syntax
```
typedef struct _DXGKARG_QUERYDEPENDENTENGINEGROUP {
  UINT      NodeOrdinal;
  UINT      EngineOrdinal;
  ULONGLONG DependentNodeOrdinalMask;
} DXGKARG_QUERYDEPENDENTENGINEGROUP;
```

## Members


`NodeOrdinal`

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being queried in a call to <a href="https://msdn.microsoft.com/42040ffc-40a3-4794-805c-7a165c47c8c9">DxgkDdiQueryDependentEngineGroup</a>.

`EngineOrdinal`

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.

`DependentNodeOrdinalMask`

[out] The bitmask that describes all dependent nodes that will be affected by a reset operation.

## Remarks
The index value <b>EngineOrdinal</b> is assumed to be identical for all dependent nodes.

See Remarks of  <a href="https://msdn.microsoft.com/42040ffc-40a3-4794-805c-7a165c47c8c9">DxgkDdiQueryDependentEngineGroup</a> for a discussion of how to compute the bitmask in the <b>DependentNodeOrdinalMask</b> member.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/42040ffc-40a3-4794-805c-7a165c47c8c9">DxgkDdiQueryDependentEngineGroup</a>



<a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a>