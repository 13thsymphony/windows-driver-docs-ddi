---
UID: NS:d3dkmthk._D3DKMT_DESTROYHWQUEUE
title: "_D3DKMT_DESTROYHWQUEUE"
author: windows-driver-content
description: A structure holding information to destroy a hardware queue.
old-location: display\d3dkmt_destroyhwqueue.htm
old-project: display
ms.assetid: 076B47F5-8312-43E3-AE75-D4DDA8C0A181
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_DESTROYHWQUEUE structure [Display Devices], display.d3dkmt_destroyhwqueue, D3DKMT_DESTROYHWQUEUE, _D3DKMT_DESTROYHWQUEUE, d3dkmthk/D3DKMT_DESTROYHWQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_DESTROYHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYHWQUEUE
---

# _D3DKMT_DESTROYHWQUEUE structure
A structure holding information to destroy a hardware queue.

## Syntax
````
typedef struct _D3DKMT_DESTROYHWQUEUE {
  D3DKMT_HANDLE hHwQueue;
} D3DKMT_DESTROYHWQUEUE;
````

## Members


`hHwQueue`

Handle to the hardware queue to be destroyed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |