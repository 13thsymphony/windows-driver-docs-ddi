---
UID : NC:d3dkmddi.DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
title : DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
author : windows-driver-content
description : Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.
old-location : display\dxgkddi_postmultiplaneoverlaypresent.htm
old-project : display
ms.assetid : C420DDE8-73D4-4D43-861C-A7B31B4C7DEC
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api : DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT
req.alt-loc : d3dkmddi.h
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
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT function
Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.

## Syntax

```
DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT DxgkddiPostmultiplaneoverlaypresent;

NTSTATUS DxgkddiPostmultiplaneoverlaypresent(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_POSTMULTIPLANEOVERLAYPRESENT pPostPresent
)
{...}
```

## Parameters

`hAdapter`

Identifies the adapter containing the overlay hardware.

`pPostPresent`




## Return Value

DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT returns the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>If the routine has been successfully completed. The driver should always return a success code.  Failures will result in a bugcheck.

## Remarks

This function is called from PASSIVE level.

This function is only called when driver sets PostPresentNeeded of DXGKCB_NOTIFY_MPO_VSYNC_FLAGS member of the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure in the VSYNC callback.

The driver can use this function to lower voltage levels, clocks, FIFO depths, or any other optimization that can save power.

The driver should not spend significant amount of time in this call because the call blocks the main GPU scheduler thread and delay could lead to present glitches. Time intensive actions should be queued as separate work items by driver and handled in background. In this scenario, any conflicts between the queued item and hardware changes demanded by future pre/post calls should be managed by driver. </p>

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