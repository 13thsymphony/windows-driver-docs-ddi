---
UID: NF:wdm.ExReInitializeRundownProtection
title: ExReInitializeRundownProtection function
author: windows-driver-content
description: The ExReInitializeRundownProtection routine reinitializes an EX_RUNDOWN_REF structure after the associated object is run down.
old-location: kernel\exreinitializerundownprotection.htm
old-project: kernel
ms.assetid: 41B7CE15-8702-49C8-9FD0-450DF6E4798C
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExReInitializeRundownProtection, ExReInitializeRundownProtection routine [Kernel-Mode Driver Architecture], kernel.exreinitializerundownprotection, wdm/ExReInitializeRundownProtection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExReInitializeRundownProtection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExReInitializeRundownProtection function
The <b>ExReInitializeRundownProtection</b> routine reinitializes an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure after the associated object is run down.

## Syntax

```
NTKERNELAPI VOID ExReInitializeRundownProtection(
  PEX_RUNDOWN_REF RunRef
);
```

## Parameters

`RunRef`

A pointer to an <b>EX_RUNDOWN_REF</b> structure that was initialized by a previous call to the  <a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.


## Return Value

None.

## Remarks

This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers.

<b>ExReInitializeRundownProtection</b> enables a previously used <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure to be associated with a new object, and initializes run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> to acquire run-down protection on the new object.

An <b>ExReInitializeRundownProtection</b> call must be preceded by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569378">ExWaitForRundownProtectionRelease</a> routine that runs down the old object. Between the <b>ExWaitForRundownProtectionRelease</b> and <b>ExReInitializeRundownProtection</b> calls, the driver might call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569377">ExRundownCompleted</a> routine to indicate that the run down of the old object has completed.

On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the old object was run down. Otherwise, <b>ExReInitializeRundownProtection</b> bug checks in checked builds.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows XP.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569377">ExRundownCompleted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569378">ExWaitForRundownProtectionRelease</a>