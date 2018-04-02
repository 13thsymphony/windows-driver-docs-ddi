---
UID: NC:fltkernel.PFLT_GET_OPERATION_STATUS_CALLBACK
title: PFLT_GET_OPERATION_STATUS_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_GET_OPERATION_STATUS_CALLBACK as the minifilter driver's OperationStatusCallback routine.
old-location: ifsk\PFLT_GET_OPERATION_STATUS_CALLBACK.htm
old-project: ifsk
ms.assetid: f3fedf69-260c-4117-b302-db3ce6b182a0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: OperationStatusCallback, OperationStatusCallback routine [Installable File System Drivers], PFLT_GET_OPERATION_STATUS_CALLBACK, fltkernel/OperationStatusCallback, ifsk.PFLT_GET_OPERATION_STATUS_CALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	FltKernel.h
api_name:
-	OperationStatusCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# PFLT_GET_OPERATION_STATUS_CALLBACK callback function
A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine.

## Syntax

```
PFLT_GET_OPERATION_STATUS_CALLBACK PfltGetOperationStatusCallback;

void PfltGetOperationStatusCallback(
  PCFLT_RELATED_OBJECTS FltObjects,
  PFLT_IO_PARAMETER_BLOCK IopbSnapshot,
  NTSTATUS OperationStatus,
  PVOID RequesterContext
)
{...}
```

## Parameters

`FltObjects`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation.

`IopbSnapshot`

A pointer to the data structure containing parameters from the IO Request Packet for the operation.

`OperationStatus`

The NTSTATUS value of the I/O operation generating the callback.

`RequesterContext`

An optional pointer to a minifilter driver-provided context information of the requester passed from <a href="https://msdn.microsoft.com/library/windows/hardware/ff544346">FltRequestOperationStatusCallback</a>.


## Return Value

This routine does not return a value.

## Remarks

A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine. 



Most minifilter drivers never need to register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i>. Normally, a minifilter driver only calls this routine to determine whether a requested opportunistic lock was granted.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.  |
| **Target Platform** | Desktop |
| **Header** | fltkernel.h (include FltKernel.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544638">FLT_IO_PARAMETER_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544346">FltRequestOperationStatusCallback</a>