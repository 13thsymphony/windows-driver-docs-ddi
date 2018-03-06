---
UID: NC:d3d12umddi.PFND3D12DDI_SETVIEWINSTANCEMASK_0033
title: PFND3D12DDI_SETVIEWINSTANCEMASK_0033
author: windows-driver-content
description: Used to set a view instance mask.
old-location: display\pfnd3d12ddi_setviewinstancemask_0033.htm
old-project: display
ms.assetid: 0A41AC01-9F45-4026-9451-AEF2732C9084
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_SETVIEWINSTANCEMASK_0033, PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback function [Display Devices], d3d12umddi/PFND3D12DDI_SETVIEWINSTANCEMASK_0033, display.pfnd3d12ddi_setviewinstancemask_0033
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
-	PFND3D12DDI_SETVIEWINSTANCEMASK_0033
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback function
Used to set a view instance mask.

## Syntax

```
PFND3D12DDI_SETVIEWINSTANCEMASK_0033 Pfnd3d12ddiSetviewinstancemask0033;

void Pfnd3d12ddiSetviewinstancemask0033(
   D3D12DDI_HCOMMANDLIST,
  UINT Mask
)
{...}
```

## Parameters

`D3D12DDI_HCOMMANDLIST`



`Mask`

The mask that will be set.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |