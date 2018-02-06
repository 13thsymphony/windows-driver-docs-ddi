---
UID: NC:d3dkmddi.DXGKDDI_MAPCPUHOSTAPERTURE
title: DXGKDDI_MAPCPUHOSTAPERTURE
author: windows-driver-content
description: DxgkDdiMapCpuHostAperture is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.
old-location: display\dxgkddimapcpuhostaperture.htm
old-project: display
ms.assetid: 78729B9A-A9FA-4D1E-8D30-3FFD61B1A7D3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddimapcpuhostaperture, DxgkDdiMapCpuHostAperture callback function [Display Devices], DxgkDdiMapCpuHostAperture, DXGKDDI_MAPCPUHOSTAPERTURE, DXGKDDI_MAPCPUHOSTAPERTURE, d3dkmddi/DxgkDdiMapCpuHostAperture
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiMapCpuHostAperture
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_MAPCPUHOSTAPERTURE function
<b>DxgkDdiMapCpuHostAperture</b> is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.

## Syntax

```
DXGKDDI_MAPCPUHOSTAPERTURE DxgkddiMapcpuhostaperture;

NTSTATUS DxgkddiMapcpuhostaperture(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_MAPCPUHOSTAPERTURE pArgs
)
{...}
```

## Parameters

`hAdapter`

A handle to the display adapter.

`pArgs`




## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |