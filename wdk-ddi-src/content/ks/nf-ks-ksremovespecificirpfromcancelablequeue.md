---
UID: NF:ks.KsRemoveSpecificIrpFromCancelableQueue
title: KsRemoveSpecificIrpFromCancelableQueue function
author: windows-driver-content
description: The KsRemoveSpecificIrpFromCancelableQueue function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using KsRemoveIrpFromCancelableQueue, but that was not actually removed from the queue.
old-location: stream\ksremovespecificirpfromcancelablequeue.htm
old-project: stream
ms.assetid: 2d3550c3-4a06-410e-9ec9-fed8b2786092
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsRemoveSpecificIrpFromCancelableQueue, KsRemoveSpecificIrpFromCancelableQueue function [Streaming Media Devices], ks/KsRemoveSpecificIrpFromCancelableQueue, ksfunc_db7aeb28-a39d-4ab6-9df5-6eef83453c85.xml, stream.ksremovespecificirpfromcancelablequeue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsRemoveSpecificIrpFromCancelableQueue
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsRemoveSpecificIrpFromCancelableQueue function
The <b>KsRemoveSpecificIrpFromCancelableQueue</b> function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using <a href="https://msdn.microsoft.com/library/windows/hardware/ff566795">KsRemoveIrpFromCancelableQueue</a>, but that was not actually removed from the queue.

## Syntax

```
KSDDKAPI VOID KsRemoveSpecificIrpFromCancelableQueue(
  PIRP Irp
);
```

## Parameters

`Irp`

Points to I/O request packet.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |