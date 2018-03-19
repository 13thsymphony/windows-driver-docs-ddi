---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB
author: windows-driver-content
description: pfnWaitForSynchronizationObjectFromGpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromgpucb.htm
old-project: display
ms.assetid: 49023D25-D57E-418F-AD10-133377B90493
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB, d3dumddi/pfnWaitForSynchronizationObjectFromGpuCb, display.pfnwaitforsynchronizationobjectfromgpucb, pfnWaitForSynchronizationObjectFromGpuCb, pfnWaitForSynchronizationObjectFromGpuCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnWaitForSynchronizationObjectFromGpuCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB callback function
<b>pfnWaitForSynchronizationObjectFromGpuCb</b> waits for a monitored fence to reach a certain value before processing subsequent context commands. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <b>pfnWaitForSynchronizationObjectFromGpuCb</b>, as it supports all synchronization object types.

## Syntax

```
PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB Pfnd3dddiWaitforsynchronizationobjectfromgpucb;

HRESULT Pfnd3dddiWaitforsynchronizationobjectfromgpucb(
  HANDLE hDevice,
  CONST D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device.

`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function semantics are similar to existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> call, except that this callback also supports monitored fence objects and an array of monitored fence values to wait for.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_waitforsynchronizationobjectfromgpu.md">D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>



<i>pfnWaitForSynchronizationObject2Cb</i>