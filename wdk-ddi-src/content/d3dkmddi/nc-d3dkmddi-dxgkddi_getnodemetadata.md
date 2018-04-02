---
UID: NC:d3dkmddi.DXGKDDI_GETNODEMETADATA
title: DXGKDDI_GETNODEMETADATA
author: windows-driver-content
description: From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.
old-location: display\dxgkddigetnodemetadata.htm
old-project: display
ms.assetid: ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_GETNODEMETADATA, DxgkDdiGetNodeMetadata, DxgkDdiGetNodeMetadata callback function [Display Devices], d3dkmddi/DxgkDdiGetNodeMetadata, display.dxgkddigetnodemetadata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiGetNodeMetadata
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_GETNODEMETADATA callback function
From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.

## Syntax

```
DXGKDDI_GETNODEMETADATA DxgkddiGetnodemetadata;

NTSTATUS DxgkddiGetnodemetadata(
  IN_CONST_HANDLE hAdapter,
  UINT NodeOrdinalAndAdapterIndex,
  OUT_PDXGKARG_GETNODEMETADATA pGetNodeMetadata
)
{...}
```

## Parameters

`hAdapter`

[in] A handle that identifies a display adapter. The DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.

`NodeOrdinalAndAdapterIndex`



`pGetNodeMetadata`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265405">DXGKARG_GETNODEMETADATA</a> structure that contains the engine type and friendly name of the engine specified by the <i>NodeOrdinal</i> parameter.


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

<a href="https://msdn.microsoft.com/ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6">DxgkDdiGetNodeMetadata</a> successfully retrieved the engine information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller-provided <i>hAdapter</i> or <i>pGetNodeMetadata</i> parameters are invalid, or the caller-provided value of <i>NodeOrdinal</i> is greater than or equal to the number of nodes on the adapter.

</td>
</tr>
</table>
 

If the <i>hAdapter</i> and <i>pGetNodeMetadata</i> parameters are valid, and <i>NodeOrdinal</i> has a value in the range of 0 to (number of nodes - 1), all calls to this function must be successful.

## Remarks

For more information on how to implement this function, see <a href="https://msdn.microsoft.com/822FEB3E-A39D-4B33-BD9D-F3166EF99AF8">Enumerating GPU engine capabilities</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265405">DXGKARG_GETNODEMETADATA</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>