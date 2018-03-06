---
UID: NS:d3dkmthk._D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: "_D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY"
author: windows-driver-content
description: Describes information that is required for an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmt_getcontextinprocessschedulingpriority.htm
old-project: display
ms.assetid: a72dd755-efd9-4950-8400-179eb1d63e9a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure [Display Devices], _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, d3dkmthk/D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, display.d3dkmt_getcontextinprocessschedulingpriority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
---

# _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure
Describes information that is required for an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.

## Syntax
````
typedef struct _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY {
  D3DKMT_HANDLE hContext;
  INT           Priority;
} D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY;
````

## Members


`hContext`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context to retrieve scheduling priority for.

`Priority`

[out] The priority level that is retrieved for the device context relative to other device contexts within the same process.

A value of zero indicates that the context is scheduled with the same priority as other contexts within the same process.

A value of 1 indicates that the context is scheduled ahead of other contexts within the same process.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |