---
UID: NF:dbgeng.IDebugEventCallbacksWide.LoadModule
title: IDebugEventCallbacksWide::LoadModule method
author: windows-driver-content
description: The LoadModule callback method is called by the engine when a module-load debugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_loadmodule.htm
old-project: Debugger
ms.assetid: 03a76d41-3af1-48a9-832a-1c255a8b0cc4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugEventCallbacksWide, LoadModule method [Windows Debugging], dbgeng/IDebugEventCallbacksWide::LoadModule, debugger.idebugeventcallbackswide_loadmodule, LoadModule, IDebugEventCallbacksWide::LoadModule, IDebugEventCallbacksWide interface [Windows Debugging], LoadModule method, LoadModule method [Windows Debugging], IDebugEventCallbacksWide interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugEventCallbacksWide.LoadModule
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# LoadModule method
The <b>LoadModule</b> callback method is called by the engine when a module-load debugging event occurs in the target.

## Syntax

````
HRESULT LoadModule(
  [in]           ULONG64 ImageFileHandle,
  [in]           ULONG64 BaseOffset,
  [in]           ULONG   ModuleSize,
  [in, optional] PCWSTR  ModuleName,
  [in, optional] PCWSTR  ImageName,
  [in]           ULONG   CheckSum,
  [in]           ULONG   TimeDateStamp
);
````

## Parameters

`ImageFileHandle`

Specifies the handle to the module's image file.  If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>.

`BaseOffset`

Specifies the base address of the module in the target's memory address space.  If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.

`ModuleSize`

Specifies the module's image size in bytes.  If this information is not available, <i>ModuleSize</i> will be <b>NULL</b>.

`ModuleName`

Specifies the simplified module name that is used by the debugger engine.  In most cases, this matches the image file name excluding the extension. If this information is not available, <i>ModuleName</i> will be <b>NULL</b>.

`ImageName`

Specifies the module's image file name, which can include the path.  If this information is not available, <i>ImageName</i> will be <b>NULL</b>.

`CheckSum`

Specifies the checksum of the module's image file.  If this information is not available, <i>CheckSum</i> will be <b>NULL</b>.

`TimeDateStamp`

Specifies the time and date stamp of the module's image file.  If this information is not available, <i>TimeDateStamp</i> will be zero.


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_LOAD_MODULE flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

After calling this method, the engine will call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550587">IDebugEventCallbacksWide::ChangeSymbolState</a>, with the <i>Flags</i> parameter containing the bit flag DEBUG_CSS_LOADS.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |