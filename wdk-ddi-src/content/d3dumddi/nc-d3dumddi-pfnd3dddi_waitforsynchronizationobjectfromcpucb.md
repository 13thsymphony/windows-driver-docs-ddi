---
UID: NC:d3dumddi.PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
title: PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB
author: windows-driver-content
description: pfnWaitForSynchronizationObjectFromCpuCb waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\pfnwaitforsynchronizationobjectfromcpucb.htm
old-project: display
ms.assetid: 304A5BCE-19E6-4F92-B840-FD3BE1CFB856
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
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
req.alt-api: pfnWaitForSynchronizationObjectFromCpuCb
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB callback



## -description
<b>pfnWaitForSynchronizationObjectFromCpuCb</b> waits for a monitored fence to reach a certain value before processing subsequent context commands.



## -prototype

````
PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB pfnWaitForSynchronizationObjectFromCpuCb;

HRESULT APIENTRY CALLBACK* pfnWaitForSynchronizationObjectFromCpuCb(
         HANDLE                                      hDevice,
   const D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *pData
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device.


### -param pData 

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromcpu.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</a> structure that provides the details of the requested operation.


## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
