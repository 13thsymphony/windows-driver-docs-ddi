---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: Notifies the user-mode display driver about the new location of the driver function table. Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\relocatedevicefuncs_d3d11_2_.htm
old-project: display
ms.assetid: BA2A1F90-6E30-4055-9374-943540AE2446
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS, RelocateDeviceFuncs(D3D11_2), RelocateDeviceFuncs(D3D11_2) callback function [Display Devices], d3d10umddi/RelocateDeviceFuncs(D3D11_2), display.relocatedevicefuncs_d3d11_2_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	RelocateDeviceFuncs(D3D11_2)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS callback function
Notifies the user-mode display driver about the new location of the driver function table.

Implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## Syntax

```
PFND3DWDDM1_3DDI_RELOCATEDEVICEFUNCS Pfnd3dwddm13DdiRelocatedevicefuncs;

void Pfnd3dwddm13DdiRelocatedevicefuncs(
   D3D10DDI_HDEVICE,
  D3DWDDM1_3DDI_DEVICEFUNCS *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code.

## Remarks

A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11_2)</i> function to replace function pointers in the driver function table.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/BA2A1F90-6E30-4055-9374-943540AE2446">RelocateDeviceFuncs(D3D11_2)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>