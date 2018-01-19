---
UID : NF:dbgeng.IDebugEventCallbacksWide.Exception
title : IDebugEventCallbacksWide::Exception method
author : windows-driver-content
description : The Exception callback method is called by the engine when an exceptiondebugging event occurs in the target.
old-location : debugger\idebugeventcallbackswide_exception.htm
old-project : debugger
ms.assetid : 02f5bec1-f2d2-4b72-bd9e-b30315c334da
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugEventCallbacksWide, IDebugEventCallbacksWide::Exception, Exception
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
req.alt-api : IDebugEventCallbacksWide.Exception
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


# Exception method
The <b>Exception</b> callback method is called by the engine when an <a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a>debugging event occurs in the target.

## Syntax

````
HRESULT Exception(
  [in] PEXCEPTION_RECORD64 Exception,
  [in] ULONG               FirstChance
);
````

## Parameters

`Exception`

Specifies the nature of the exception.  EXCEPTION_RECORD64 is defined in Winnt.h.

`FirstChance`

Specifies whether this exception has been previously encountered.  A nonzero value means that this is the first time the exception has been encountered ("first chance").  A zero value means that the exception has already been offered to all possible handlers, and each one declined to handle it ("second chance").


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_EXCEPTION flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

Because the structure that <i>Exception</i> points to might be deleted after this method returns, implementations of <b>IDebugEventCallbacksWide</b> should not access this structure after returning.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>

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