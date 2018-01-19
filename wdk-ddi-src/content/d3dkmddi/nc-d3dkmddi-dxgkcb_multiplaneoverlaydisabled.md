---
UID : NC:d3dkmddi.DXGKCB_MULTIPLANEOVERLAYDISABLED
title : DXGKCB_MULTIPLANEOVERLAYDISABLED
author : windows-driver-content
description : This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId.
old-location : display\dxgkcb_multiplaneoverlaydisabled.htm
old-project : display
ms.assetid : EA9FAB26-1EAF-4E67-B240-094BC2B03DEF
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
req.alt-api : DXGKCB_MULTIPLANEOVERLAYDISABLED
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
req.irql : requires_max_(PASSIVE_LEVEL)
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKCB_MULTIPLANEOVERLAYDISABLED callback function
This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId.

## Syntax

```
DXGKCB_MULTIPLANEOVERLAYDISABLED DxgkcbMultiplaneoverlaydisabled;

void DxgkcbMultiplaneoverlaydisabled(
  IN_CONST_HANDLE hAdapter,
  UINT VidPnSourceId
)
{...}
```

## Parameters

`hAdapter`

Indicates the adapter on which the current multiplane overlay hardware configuration is no longer supported.

`VidPnSourceId`

Indicates the VidPnSourceId on which the current multiplane overlay hardware configuration is no longer supported.


## Return Value

DXGKCB_MULTIPLANEOVERLAYDISABLED returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>If the call has been successfully completed.

## Remarks

This callback will notify the DWM that the current MPO configuration is no longer supported, allowing the DWM to fall back to composition. 

This callback can only be called at passive level.


This callback can be used in the following scenarios:

</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h |
| **Library** |  |
| **IRQL** | requires_max_(PASSIVE_LEVEL) |
| **DDI compliance rules** |  |