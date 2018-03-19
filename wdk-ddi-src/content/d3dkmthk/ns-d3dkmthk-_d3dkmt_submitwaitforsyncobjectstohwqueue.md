---
UID: NS:d3dkmthk._D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
title: "_D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE"
author: windows-driver-content
description: A structure that contains information to submit a wait on the hardware queue.
old-location: display\d3dkmt_submitwaitforsyncobjectstohwqueue_.htm
old-project: display
ms.assetid: 365253FC-9FC0-4FFF-9D84-503754095327
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, d3dkmthk/D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, display.d3dkmt_submitwaitforsyncobjectstohwqueue_
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
product: Windows
targetos: Windows
req.typenames: D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
---

# _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure
A structure that contains information to submit a wait on the hardware queue.

## Syntax
````
typedef struct _D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE  {
  D3DKMT_HANDLE       hHwQueue;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  const UINT64        *FenceValueArray;
} D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE ;
````

## Members


`hHwQueue`

Context queue to submit the command to.

`ObjectCount`

Number of objects to wait on.

`ObjectHandleArray`

Handles to monitored fence synchronization objects to wait on.

`FenceValueArray`

Monitored fence values to be waited.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |