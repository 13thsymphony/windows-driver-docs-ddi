---
UID: NF.irb.AtaPortRequestWorkerRoutine
title: AtaPortRequestWorkerRoutine function
author: windows-driver-content
description: The AtaPortRequestWorkerRoutine routine requests a worker routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestworkerroutine.htm
old-project: storage
ms.assetid: 2d9a6886-aeec-4d61-8c9d-056d1409b905
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: AtaPortRequestWorkerRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AtaPortRequestWorkerRoutine
req.alt-loc: irb.h
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
---

# AtaPortRequestWorkerRoutine function



## -description
The <b>AtaPortRequestWorkerRoutine</b> routine requests a worker routine.



## -syntax

````
BOOLEAN __inline AtaPortRequestWorkerRoutine(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC WorkerRoutine
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param WorkerRoutine [in]

A pointer of type IDE_HW_DPC to the worker routine to call. 


## -returns
None 


## -remarks
The miniport driver can request a worker routine to perform tasks that cannot be done in the interrupt service routine. Transferring operations to a worker routine is an effective way to keep the interrupt service routine as small as possible.

The worker routine is not synchronized with the interrupt. 

When the port driver calls the worker routine, the port driver will pass the pointer to the channel extension that is stored in <i>ChannelExtension</i>.

The <i>WorkerRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Irb.h (include Ata.h or Irb.h)</dt>
</dl>
</td>
</tr>
</table>