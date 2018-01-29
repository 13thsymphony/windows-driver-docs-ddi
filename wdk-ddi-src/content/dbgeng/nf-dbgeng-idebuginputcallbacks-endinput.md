---
UID : NF:dbgeng.IDebugInputCallbacks.EndInput
title : IDebugInputCallbacks::EndInput method
author : windows-driver-content
description : The EndInput callback method is called by the engine to indicate that it is no longer waiting for input.
old-location : debugger\idebuginputcallbacks_endinput.htm
old-project : debugger
ms.assetid : e22b616c-51f6-4687-95b0-eb833ceb9ec3
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugInputCallbacks::EndInput, EndInput method [Windows Debugging], IDebugInputCallbacks interface, IDebugInputCallbacks interface [Windows Debugging], EndInput method, ComCallbacks_3e06dd1c-483b-4934-83d5-b00241d9d88b.xml, IDebugInputCallbacks, EndInput method [Windows Debugging], EndInput, IDebugInputCallbacks::EndInput, debugger.idebuginputcallbacks_endinput
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# EndInput method
The <b>EndInput</b> callback method is called by the engine to indicate that it is no longer waiting for input.

## Syntax

````
HRESULT EndInput();
````

## Parameters

This function has no parameters.

## Return Value

This method's return value is ignored by the engine.

## Remarks

Even if the engine has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff550797">IDebugInputCallbacks::StartInput</a> for this <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> object, the engine will call <b>EndInput</b> if another IDebugInputCallbacks object returned an error from the <b>IDebugInputCallbacks::StartInput</b> method.

For more information about debugger engine input, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.

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