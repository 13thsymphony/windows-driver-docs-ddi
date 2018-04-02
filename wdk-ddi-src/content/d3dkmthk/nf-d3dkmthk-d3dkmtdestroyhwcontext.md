---
UID: NF:d3dkmthk.D3DKMTDestroyHwContext
title: D3DKMTDestroyHwContext function
author: windows-driver-content
description: Used to destroy a hardware context.
old-location: display\d3dkmtdestroyhwcontext.htm
old-project: display
ms.assetid: 832CA7CA-40B3-4D6D-B640-9838B479EC76
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTDestroyHwContext, D3DKMTDestroyHwContext function [Display Devices], d3dkmthk/D3DKMTDestroyHwContext, display.d3dkmtdestroyhwcontext
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
-	D3DKMTDestroyHwContext
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyHwContext function
Used to destroy a hardware context.

## Syntax

```
NTSTATUS D3DKMTDestroyHwContext(
  CONST *D3DKMT_DESTROYHWCONTEXT
);
```

## Parameters

`D3DKMT_DESTROYHWCONTEXT`

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