---
UID: NS.d3dumddi._D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
author: windows-driver-content
description: A structure that holds information to submit a signal synchronization object to a hardware queue.
old-location: display\d3dddicb_submitsignalsyncobjectstohwqueue.htm
old-project: display
ms.assetid: 22AA35D4-D287-443B-A49D-87C20BD436AA
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE, D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
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
req.alt-api: D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
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
req.iface: 
---

# D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE structure



## -description
<p>A structure that holds information to submit a signal synchronization object to a hardware queue.</p>


## -syntax

````
typedef struct _D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE {
  D3DDDICB_SIGNALFLAGS     Flags;
  ULONG                    BroadcastHwQueueCount;
  const HANDLE             *BroadcastHwQueueArray;
  UINT                     ObjectCount;
  const D3DKMT_HANDLE      *ObjectHandleArray;
  const UINT64             *FenceValueArray;
} D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>Specifies signal behavior.</p>
</dd>

### -field <b>BroadcastHwQueueCount</b>

<dd>
<p>Specifies the number of hardware queues to broadcast this signal to.</p>
</dd>

### -field <b>BroadcastHwQueueArray</b>

<dd>
<p>Specifies hardware queue handles to broadcast to.
</p>
</dd>

### -field <b>ObjectCount</b>

<dd>
<p>Number of objects to signal.
</p>
</dd>

### -field <b>ObjectHandleArray</b>

<dd>
<p>Handles to monitored fence synchronization objects to signal.</p>
</dd>

### -field <b>FenceValueArray</b>

<dd>
<p>monitored fence values to signal.
</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h</dt>
</dl>
</td>
</tr>
</table>