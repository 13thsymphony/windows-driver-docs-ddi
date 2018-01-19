---
UID : NF:video.VideoPortGetMdl
title : VideoPortGetMdl function
author : windows-driver-content
description : The VideoPortGetMdl function is obsolete in Windows 2000 and later.VideoPortGetMdl retrieves the memory descriptor list (MDL) that represents the page table of the locked buffer.
old-location : display\videoportgetmdl.htm
old-project : display
ms.assetid : 03ec6323-a3f9-485d-80c8-92ac99d8e73a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortGetMdl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VideoPortGetMdl
req.alt-loc : Videoprt.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : 
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortGetMdl function
The <b>VideoPortGetMdl</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetMdl</b> retrieves the memory descriptor list (<a href="wdkgloss.m#wdkgloss.mdl#wdkgloss.mdl"><i>MDL</i></a>) that represents the page table of the locked buffer.

## Syntax

````
PVOID VideoPortGetMdl(
  _In_ PVOID HwDeviceExtension,
  _In_ PDMA  pDma
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pDma`

Is a handle to the DMA context being queried. This handle was obtained from <a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a> or <a href="..\video\nf-video-videoportdodma.md">VideoPortDoDma</a>.


## Return Value

<b>VideoPortGetMdl</b> returns <i>pDma</i>, for compatibility reasons.

## Remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |