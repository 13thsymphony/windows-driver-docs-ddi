---
UID: NF:dbgeng.IDebugPlmClient2.LaunchPlmBgTaskForDebugWide
title: IDebugPlmClient2::LaunchPlmBgTaskForDebugWide method
author: windows-driver-content
description: Launches a suspended Process Lifecycle Management (PLM) background task.
old-location: debugger\idebugplmclient2_launchplmbgtaskfordebugwide.htm
old-project: debugger
ms.assetid: 47793815-F7AC-4E0D-809C-DBB7497BDA30
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugPlmClient2, IDebugPlmClient2 interface [Windows Debugging], LaunchPlmBgTaskForDebugWide method, IDebugPlmClient2::LaunchPlmBgTaskForDebugWide, LaunchPlmBgTaskForDebugWide method [Windows Debugging], LaunchPlmBgTaskForDebugWide method [Windows Debugging], IDebugPlmClient2 interface, LaunchPlmBgTaskForDebugWide,IDebugPlmClient2.LaunchPlmBgTaskForDebugWide, dbgeng/IDebugPlmClient2::LaunchPlmBgTaskForDebugWide, debugger.idebugplmclient2_launchplmbgtaskfordebugwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
req.lib: 
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
-	IDebugPlmClient2.LaunchPlmBgTaskForDebugWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugPlmClient2::LaunchPlmBgTaskForDebugWide method
Launches a suspended Process Lifecycle Management (PLM) background task.

## Syntax

```
HRESULT LaunchPlmBgTaskForDebugWide(
  ULONG64 Server,
  ULONG   Timeout,
  PCWSTR  PackageFullName,
  PCWSTR  BackgroundTaskId,
  PULONG  ProcessId,
  PULONG  ThreadId
);
```

## Parameters

`Server`

The server of the task.

`Timeout`

A time-out value.

`PackageFullName`

A pointer to the package name.

`BackgroundTaskId`

A pointer to the task ID.

`ProcessId`

A pointer to a process ID output.

`ThreadId`

A pointer to a thread ID output.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/22AACAD1-292B-42D9-95F7-A3654E2077FB">IDebugPlmClient2</a>