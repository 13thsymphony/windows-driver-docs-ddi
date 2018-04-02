---
UID: NS:wdbgexts._WDBGEXTS_THREAD_OS_INFO
title: "_WDBGEXTS_THREAD_OS_INFO"
author: windows-driver-content
description: The IG_GET_THREAD_OS_INFO Ioctl operation returns information about an operating system thread in the target. When calling Ioctl with IoctlType set to IG_GET_THREAD_OS_INFO, IpvData should contain an instance of the WDBGEXTS_THREAD_OS_INFO structure.
old-location: debugger\ig_get_thread_os_info.htm
old-project: debugger
ms.assetid: 5cd1ba71-af2f-4662-b37d-88f4e4aa7624
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWDBGEXTS_THREAD_OS_INFO, PWDBGEXTS_THREAD_OS_INFO, PWDBGEXTS_THREAD_OS_INFO structure pointer [Windows Debugging], WDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO structure [Windows Debugging], WdbgExts_Ref_dfcc01ec-d4f4-4eba-adb5-d729f951f502.xml, _WDBGEXTS_THREAD_OS_INFO, debugger.ig_get_thread_os_info, wdbgexts/PWDBGEXTS_THREAD_OS_INFO, wdbgexts/WDBGEXTS_THREAD_OS_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	WDBGEXTS_THREAD_OS_INFO
product: Windows
targetos: Windows
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
req.product: Windows 10 or later.
---

# _WDBGEXTS_THREAD_OS_INFO structure
The IG_GET_THREAD_OS_INFO <a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation returns information about an operating system thread in the target.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_GET_THREAD_OS_INFO, <i>IpvData</i> should contain an instance of the WDBGEXTS_THREAD_OS_INFO structure.

## Syntax
```
typedef struct _WDBGEXTS_THREAD_OS_INFO {
  ULONG   ThreadId;
  ULONG   ExitStatus;
  ULONG   PriorityClass;
  ULONG   Priority;
  ULONG64 CreateTime;
  ULONG64 ExitTime;
  ULONG64 KernelTime;
  ULONG64 UserTime;
  ULONG64 StartOffset;
  ULONG64 Affinity;
} WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO;
```

## Members


`ThreadId`

Specifies the operating system thread ID (within the current process) for the thread whose information is being requested.

`ExitStatus`

Receives the exit code of the thread.  If the thread is still running or the exit code is not known, <b>ExitStatus</b> will be set to STILL_ACTIVE.

`PriorityClass`

Receives the priority class of the thread.  The priority classes are defined by the constants <i>XXX</i>_PRIORITY_CLASS in WinBase.h.  See the Platform SDK for more information about thread priority classes.  If the priority class is not know, <b>PriorityClass</b> will be set to zero.

`Priority`

Receives the priority of the thread relative to the priority class.  Some thread priorities are defined by the constants THREAD_PRIORITY_<i>XXX</i> in WinBase.h.  See the Platform SDK for more information about thread priorities.  If the priority is not known, <b>Priority</b> will be set to THREAD_PRIORITY_NORMAL.

`CreateTime`

Receives the creation time of the thread.

`ExitTime`

Receives the exit time of the thread.  If the thread has not exited, <b>ExitTime</b> is undefined.

`KernelTime`

Receives the amount of time that the thread has executed in kernel mode.

`UserTime`

Receives the amount of time that the thread has executed in user-mode.

`StartOffset`

Receives the starting address of the thread.  If the starting address is not known, <b>StartOffset</b> will be set to zero.

`Affinity`

Receives the thread affinity mask for the thread in a symmetric multiprocessor (SMP) computer.  See the Platform SDK for more information about the thread affinity mask.  If the affinity mask is not known, <b>Affinity</b> is set to zero.

## Remarks
The parameters for the IG_GET_THREAD_OS_INFO <a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a> operation are the members of the WDBGEXTS_THREAD_OS_INFO structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a>