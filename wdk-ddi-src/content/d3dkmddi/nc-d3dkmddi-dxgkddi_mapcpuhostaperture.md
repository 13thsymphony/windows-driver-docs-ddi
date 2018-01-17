---
UID: NC:d3dkmddi.DXGKDDI_MAPCPUHOSTAPERTURE
title: DXGKDDI_MAPCPUHOSTAPERTURE function
author: windows-driver-content
description: DxgkDdiMapCpuHostAperture is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.
old-location: display\dxgkddimapcpuhostaperture.htm
old-project: display
ms.assetid: 78729B9A-A9FA-4D1E-8D30-3FFD61B1A7D3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_MAPCPUHOSTAPERTURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiMapCpuHostAperture
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
req.irql: 
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_MAPCPUHOSTAPERTURE function



## -description
<b>DxgkDdiMapCpuHostAperture</b> is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.



## -syntax

````
DXGKDDI_MAPCPUHOSTAPERTURE DxgkDdiMapCpuHostAperture;

NTSTATUS APIENTRY DxgkDdiMapCpuHostAperture(
  _In_ HANDLE                     hAdapter,
  _In_ DXGKARG_MAPCPUHOSTAPERTURE *Map
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to the display adapter.


### -param Map [in]

The <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_mapcpuhostaperture.md">DXGKARG_MAPCPUHOSTAPERTURE</a> structure that describes the operation.


## -returns

      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.


## -remarks
