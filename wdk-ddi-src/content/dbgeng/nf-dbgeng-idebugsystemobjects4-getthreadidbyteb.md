---
UID : NF:dbgeng.IDebugSystemObjects4.GetThreadIdByTeb
title : IDebugSystemObjects4::GetThreadIdByTeb method
author : windows-driver-content
description : The GetThreadIdByTeb method returns the engine thread ID of the specified thread. The thread is specified by its thread environment block (TEB).
old-location : debugger\getthreadidbyteb.htm
old-project : debugger
ms.assetid : 64b98d8b-883b-4a2c-a5de-058bb3b732df
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugSystemObjects4, IDebugSystemObjects4::GetThreadIdByTeb, GetThreadIdByTeb
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugSystemObjects.GetThreadIdByTeb,IDebugSystemObjects2.GetThreadIdByTeb,IDebugSystemObjects3.GetThreadIdByTeb,IDebugSystemObjects4.GetThreadIdByTeb
req.alt-loc : dbgeng.h
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
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetThreadIdByTeb method
The <b>GetThreadIdByTeb</b> method returns the engine thread ID of the specified thread.  The thread is specified by its thread environment block (TEB).

## Syntax

````
HRESULT GetThreadIdByTeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````

## Parameters

`Offset`

Specifies the location of the thread's TEB.

`Id`

Receives the engine thread ID.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

In kernel-mode debugging, this method returns the engine thread ID for the virtual thread representing the processor on which the specified thread is executing.  If the thread is not executing on a processor, this method will fail.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |