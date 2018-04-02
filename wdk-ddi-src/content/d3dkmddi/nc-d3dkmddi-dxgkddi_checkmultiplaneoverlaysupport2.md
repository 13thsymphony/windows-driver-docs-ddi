---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
author: windows-driver-content
description: DxgkDdiCheckMultiPlaneOverlaySupport2 is called to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkddicheckmultiplaneoverlaysupport2.htm
old-project: display
ms.assetid: A453B59F-0DD1-4FFF-A0E6-09494211780F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2, DxgkDdiCheckMultiPlaneOverlaySupport2, DxgkDdiCheckMultiPlaneOverlaySupport2 callback function [Display Devices], d3dkmddi/DxgkDdiCheckMultiPlaneOverlaySupport2, display.dxgkddicheckmultiplaneoverlaysupport2
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiCheckMultiPlaneOverlaySupport2
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function
<b>DxgkDdiCheckMultiPlaneOverlaySupport2</b> is called to determine whether a specific multi-plane overlay configuration is supported.  It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.

## Syntax

```
DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 DxgkddiCheckmultiplaneoverlaysupport2;

NTSTATUS DxgkddiCheckmultiplaneoverlaysupport2(
  IN_CONST_HANDLE hAdapter,
  IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 pCheckMultiPlaneOverlaySupport
)
{...}
```

## Parameters

`hAdapter`

Identifies the adapter containing the overlay hardware.

`pCheckMultiPlaneOverlaySupport`




## Return Value

If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.

## Remarks

The kernel mode driver reports whether the specified configuration is supported.  The kernel mode driver should not raise or lower the available bandwidth in anticipation to this configuration getting set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn914469">DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2</a>