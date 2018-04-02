---
UID: NS:d3dumddi._D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
title: "_D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE"
author: windows-driver-content
description: A structure that holds information to wait for synchronized objects.
old-location: display\d3dddicb_submitwaitforsyncobjectstohwqueue.htm
old-project: display
ms.assetid: 9890EB61-2CED-41AB-9A87-76D5020D84A0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, d3dumddi/D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, display.d3dddicb_submitwaitforsyncobjectstohwqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
---

# _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure
A structure that holds information to wait for synchronized objects.

## Syntax
```
typedef struct _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE {
  HANDLE              hHwQueue;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  const UINT64        *FenceValueArray;
} D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE;
```

## Members


`hHwQueue`

Hardware queue to queue the wait on.

`ObjectCount`

Number of objects to wait on.

`ObjectHandleArray`

Handles to monitored fence synchronization objects to wait on.

`FenceValueArray`

Monitored fence values to be waited on.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dumddi.h |