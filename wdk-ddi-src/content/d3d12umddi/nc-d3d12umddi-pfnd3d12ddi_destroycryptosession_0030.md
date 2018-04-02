---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCRYPTOSESSION_0030
title: PFND3D12DDI_DESTROYCRYPTOSESSION_0030
author: windows-driver-content
description: Used to destroy a crypto session.
old-location: display\pfnd3d12ddi_destroycryptosession_0030_.htm
old-project: display
ms.assetid: 1A16AE54-8A39-419E-B664-366287CF396D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_DESTROYCRYPTOSESSION_0030, PFND3D12DDI_DESTROYCRYPTOSESSION_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_DESTROYCRYPTOSESSION_0030, display.pfnd3d12ddi_destroycryptosession_0030_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_DESTROYCRYPTOSESSION_0030
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_DESTROYCRYPTOSESSION_0030 callback function
Used to destroy a crypto session.

## Syntax

```
PFND3D12DDI_DESTROYCRYPTOSESSION_0030 Pfnd3d12ddiDestroycryptosession0030;

void Pfnd3d12ddiDestroycryptosession0030(
  D3D12DDI_HDEVICE hDrvDevice,
  D3D12DDI_HCRYPTOSESSION_0030 hDrvCryptoSession
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`hDrvCryptoSession`

The crypto session


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |