---
UID : NF:irb.AtaPortRequestWorkerRoutine
title : AtaPortRequestWorkerRoutine function
author : windows-driver-content
description : The AtaPortRequestWorkerRoutine routine requests a worker routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ataportrequestworkerroutine.htm
old-project : storage
ms.assetid : 2d9a6886-aeec-4d61-8c9d-056d1409b905
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : AtaPortRequestWorkerRoutine
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : irb.h
req.include-header : Ata.h, Irb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AtaPortRequestWorkerRoutine
req.alt-loc : irb.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : IDE_POWER_STATE
---


# AtaPortRequestWorkerRoutine function
The <b>AtaPortRequestWorkerRoutine</b> routine requests a worker routine.

## Syntax

````
BOOLEAN __inline AtaPortRequestWorkerRoutine(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC WorkerRoutine
);
````

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`CallBackRoutine`




## Return Value

None

## Remarks

The miniport driver can request a worker routine to perform tasks that cannot be done in the interrupt service routine. Transferring operations to a worker routine is an effective way to keep the interrupt service routine as small as possible.

The worker routine is not synchronized with the interrupt. 

When the port driver calls the worker routine, the port driver will pass the pointer to the channel extension that is stored in <i>ChannelExtension</i>.

The <i>WorkerRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |