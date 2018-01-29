---
UID : NC:d3dkmddi.DXGKDDI_GETPOSTCOMPOSITIONCAPS
title : DXGKDDI_GETPOSTCOMPOSITIONCAPS
author : windows-driver-content
description : Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.
old-location : display\dxgkddi_getpostcompositioncaps.htm
old-project : display
ms.assetid : B79959EC-A064-4B35-98EF-5B032AF5D4B4
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgkddi_getpostcompositioncaps, DXGKDDI_GETPOSTCOMPOSITIONCAPS callback function [Display Devices], DXGKDDI_GETPOSTCOMPOSITIONCAPS, d3dkmddi/DXGKDDI_GETPOSTCOMPOSITIONCAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dkmddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_GETPOSTCOMPOSITIONCAPS function
Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling.

## Syntax

```
DXGKDDI_GETPOSTCOMPOSITIONCAPS DxgkddiGetpostcompositioncaps;

NTSTATUS DxgkddiGetpostcompositioncaps(
  IN_CONST_HANDLE hAdapter,
  IN_OUT_PDXGKARG_GETPOSTCOMPOSITIONCAPS pGetPostCompositionCaps
)
{...}
```

## Parameters

`hAdapter`

Identifies the adapter containing the overlay hardware.

`pGetPostCompositionCaps`




## Return Value

DXGKDDI_GETPOSTCOMPOSITIONCAPS returns the following values:
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
If the routine has been successfully completed.

</td>
</tr>
</table>

## Remarks

This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |