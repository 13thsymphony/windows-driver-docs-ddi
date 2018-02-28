---
UID: NF:d3dkmthk.D3DKMTDestroyHwQueue
title: D3DKMTDestroyHwQueue function
author: windows-driver-content
description: Used to destroy a hardware queue.
old-location: display\d3dkmtdestroyhwqueue.htm
old-project: display
ms.assetid: 30687710-A813-4D3C-8612-9236D34EB9EB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTDestroyHwQueue, D3DKMTDestroyHwQueue function [Display Devices], d3dkmthk/D3DKMTDestroyHwQueue, display.d3dkmtdestroyhwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Tbd
req.dll: Tbd
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	tbd
api_name:
-	D3DKMTDestroyHwQueue
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyHwQueue function
Used to destroy a hardware queue.

## Syntax

````
NTSTATUS APIENTRY D3DKMTDestroyHwQueue(
  _In_ const D3DKMT_DESTROYHWQUEUE *destroyHwContext
);
````

## Parameters

`D3DKMT_DESTROYHWQUEUE`

TBD


## Return Value

Returns STATUS_SUCCESS if called successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3dkmthk.h |
| **Library** | Tbd |
| **DLL** | Tbd |