---
UID: NF:fltkernel.FltGetRoutineAddress
title: FltGetRoutineAddress function
author: windows-driver-content
description: The FltGetRoutineAddress routine returns a pointer to a routine specified by the FltMgrRoutineName parameter.
old-location: ifsk\fltgetroutineaddress.htm
old-project: ifsk
ms.assetid: b2b74e79-5840-41a0-8af3-3d13e209aea7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_81848969-38e3-4f2f-bdc3-45027ea28202.xml, FltGetRoutineAddress, FltGetRoutineAddress routine [Installable File System Drivers], fltkernel/FltGetRoutineAddress, ifsk.fltgetroutineaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetRoutineAddress
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetRoutineAddress function
The <b>FltGetRoutineAddress</b> routine returns a pointer to a routine specified by the <i>FltMgrRoutineName</i> parameter.

## Syntax

```
PVOID FLTAPI FltGetRoutineAddress(
  PCSTR FltMgrRoutineName
);
```

## Parameters

`FltMgrRoutineName`

Name of the filter manager routine to resolve.


## Return Value

If the routine name can be resolved, <b>FltGetRoutineAddress</b> returns a pointer to the routine. Otherwise, it returns <b>NULL</b>.

## Remarks

<b>FltGetRoutineAddress</b> searches the filter manager's export table for the requested routine name. 

To get the addresses of other routines that are exported by the kernel or hardware abstraction layer (HAL), use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554563">MmGetSystemRoutineAddress</a>. 

Note that in Windows 2000 and Windows XP, before FltGetRoutineAddress is called at least one minifilter on the system must call FltRegisterFilter. The call to FltRegisterFilter is necessary to initialize global data structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554563">MmGetSystemRoutineAddress</a>