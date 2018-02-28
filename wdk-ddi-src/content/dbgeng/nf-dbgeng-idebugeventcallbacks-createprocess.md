---
UID: NF:dbgeng.IDebugEventCallbacks.CreateProcess
title: IDebugEventCallbacks::CreateProcess method
author: windows-driver-content
description: The CreateProcess callback method is called by the engine when a create-processdebugging event occurs in the target.
old-location: debugger\idebugeventcallbacks_createprocess.htm
old-project: debugger
ms.assetid: a826782a-67ca-4b90-b7b5-caddeae6d2dc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ComCallbacks_cd6a97b7-a041-419c-8e64-0aeb6fe7b0c8.xml, CreateProcess method [Windows Debugging], CreateProcess method [Windows Debugging], IDebugEventCallbacks interface, CreateProcess,IDebugEventCallbacks.CreateProcess, IDebugEventCallbacks, IDebugEventCallbacks interface [Windows Debugging], CreateProcess method, IDebugEventCallbacks::CreateProcess, dbgeng/IDebugEventCallbacks::CreateProcess, debugger.idebugeventcallbacks_createprocess
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugEventCallbacks.CreateProcess
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# CreateProcess method
The <b>CreateProcess</b> callback method is called by the engine when a create-processdebugging event occurs in the target.

## Syntax

````
HRESULT CreateProcess(
  [in]           ULONG64 ImageFileHandle,
  [in]           ULONG64 Handle,
  [in]           ULONG64 BaseOffset,
  [in]           ULONG   ModuleSize,
  [in, optional] PCSTR   ModuleName,
  [in, optional] PCSTR   ImageName,
  [in]           ULONG   CheckSum,
  [in]           ULONG   TimeDateStamp,
  [in]           ULONG64 InitialThreadHandle,
  [in]           ULONG64 ThreadDataOffset,
  [in]           ULONG64 StartOffset
);
````

## Parameters

`ImageFileHandle`

Specifies the handle to the process's image file.    If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>.

`Handle`

Specifies the handle to the process.  This parameter corresponds to the <b>hProcess</b> field in the CREATE_PROCESS_DEBUG_INFO structure.  If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>.

`BaseOffset`

Specifies the base address of the process's executable image in the target's memory address space.  If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.

`ModuleSize`

Specifies the process's executable image size in bytes.  If this information is not available, <i>ModuleSize</i> will be zero.

`ModuleName`

Specifies the simplified module name that is used by the debugger engine.  In most cases, this matches the image file name excluding the extension.  If this information is not available, <i>ModuleName</i> will be <b>NULL</b>.

`ImageName`

Specifies the process's executable-image file name, which can include the path.   If this information is not available, <i>ImageName</i> will be <b>NULL</b>.

`CheckSum`

Specifies the checksum of the process's executable image.  If this information is not available, <i>CheckSum</i> will be zero.

`TimeDateStamp`

Specifies the time and date stamp of the process's executable-image file.  If this information is not available, <i>TimeDateStamp</i> will be zero.

`InitialThreadHandle`

Specifies the handle to the process's initial thread.  This parameter corresponds to the <b>hThread</b> field in the CREATE_PROCESS_DEBUG_INFO structure.  If this information is not available, <i>InitialThreadHandle</i> will be <b>NULL</b>.

`ThreadDataOffset`

Specifies a block of data that the operating system maintains for this thread.  The actual data in the block is operating system-specific.  If this information is not available, <i>ThreadDataOffset</i> will be <b>NULL</b>.

`StartOffset`

Specifies the starting address of the thread in the process's virtual address space.    If this information is not available, <i>StartOffset</i> will be <b>NULL</b>.


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_CREATE_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |