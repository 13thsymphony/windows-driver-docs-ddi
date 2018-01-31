---
UID : NF:portcls.IInterruptSync.RegisterServiceRoutine
title : IInterruptSync::RegisterServiceRoutine method
author : windows-driver-content
description : The RegisterServiceRoutine method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs.
old-location : audio\iinterruptsync_registerserviceroutine.htm
old-project : audio
ms.assetid : fb0650ee-24a6-4f64-9f16-dded0ccc79cd
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.iinterruptsync_registerserviceroutine, RegisterServiceRoutine method [Audio Devices], IInterruptSync::RegisterServiceRoutine, RegisterServiceRoutine, IInterruptSync, IInterruptSync interface [Audio Devices], RegisterServiceRoutine method, RegisterServiceRoutine method [Audio Devices], IInterruptSync interface, audmp-routines_92919bdc-00aa-4911-ac3c-58a0807c7212.xml, portcls/IInterruptSync::RegisterServiceRoutine
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : portcls.h
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# RegisterServiceRoutine method
The <code>RegisterServiceRoutine</code> method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs.

## Syntax

````
NTSTATUS RegisterServiceRoutine(
  [in] PINTERRUPTSYNCROUTINE Routine,
  [in] PVOID                 DynamicContext,
  [in] BOOLEAN               First
);
````

## Parameters

`Routine`

Pointer to the routine that is to be called. This parameter is a function pointer of type PINTERRUPTSYNCROUTINE (see <a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>).

`DynamicContext`

Specifies a context value that is passed to the routine when it is called.

`First`

Specifies whether the routine is added at the head or tail of the list of ISRs. If <b>TRUE</b>, the routine is added at the head of the list. If <b>FALSE</b>, it is added at the tail.


## Return Value

<code>RegisterServiceRoutine</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

This method adds the specified routine to the synchronization object's list of ISRs. When an interrupt occurs, the routine at the head of the list is called first, and the routine at the tail is called last.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |