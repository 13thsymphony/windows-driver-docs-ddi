---
UID: NC:d3dumddi.PFND3DDDI_LOGUMDMARKERCB
title: PFND3DDDI_LOGUMDMARKERCB
author: windows-driver-content
description: Called by the user-mode display driver to log a custom Event Tracing for Windows (ETW) marker event.
old-location: display\pfnlogumdmarkercb.htm
old-project: display
ms.assetid: BD544686-20D3-4577-9950-9C3B6853C4BD
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnLogUMDMarkerCb
req.alt-loc: D3dumddi.h
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_LOGUMDMARKERCB callback



## -description
Called by the user-mode display driver to log a custom Event Tracing for Windows (ETW) marker event.



## -prototype

````
PFND3DDDI_LOGUMDMARKERCB pfnLogUMDMarkerCb;

_Check_return_ HRESULT APIENTRY CALLBACK* pfnLogUMDMarkerCb(
  _In_       HANDLE                hDevice,
  _In_ const D3DDDICB_LOGUMDMARKER *pLogUMDMarker
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pLogUMDMarker [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_logumdmarker.md">D3DDDICB_LOGUMDMARKER</a> structure that indicates the location of an ETW marker event that is defined by the user-mode display driver.


## -returns

      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.


## -remarks
