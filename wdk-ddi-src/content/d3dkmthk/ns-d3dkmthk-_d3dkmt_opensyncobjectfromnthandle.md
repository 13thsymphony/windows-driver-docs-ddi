---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: "_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE"
author: windows-driver-content
description: Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmt_opensyncobjectfromnthandle.htm
old-project: display
ms.assetid: 163ce4ed-e81b-4b69-b1a7-4ea2b9e8f437
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure [Display Devices], _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, d3dkmthk/D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, display.d3dkmt_opensyncobjectfromnthandle
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
-	D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
---

# _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure
Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.

## Syntax
````
typedef struct _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE {
  HANDLE        hNtHandle;
  D3DKMT_HANDLE hSyncObject;
} D3DKMT_OPENSYNCOBJECTFROMNTHANDLE;
````

## Members


`hNtHandle`

[in] An NT handle to the process.

`hSyncObject`

[out] A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the kernel-mode synchronization object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |