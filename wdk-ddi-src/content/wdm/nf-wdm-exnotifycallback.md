---
UID: NF:wdm.ExNotifyCallback
title: ExNotifyCallback function
author: windows-driver-content
description: The ExNotifyCallback routine causes all callback routines registered for the given object to be called.
old-location: kernel\exnotifycallback.htm
old-project: kernel
ms.assetid: 5c126639-494d-45b4-81c2-1af6dc773db6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExNotifyCallback, ExNotifyCallback routine [Kernel-Mode Driver Architecture], kernel.exnotifycallback, wdm/ExNotifyCallback, k102_befd9baa-99b3-427b-a0c3-4287e5563482.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExNotifyCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExNotifyCallback function
The <b>ExNotifyCallback</b> routine causes all callback routines registered for the given object to be called.

## Syntax

````
VOID ExNotifyCallback(
  _In_     PVOID CallbackObject,
  _In_opt_ PVOID Argument1,
  _In_opt_ PVOID Argument2
);
````

## Parameters

`CallbackObject`

A pointer to the callback object for which all registered callback routines will be called.

`Argument1`

Specifies the parameter that is passed as <i>Argument1</i> of the callback routine.

`Argument2`

Specifies the parameter that is passed as <i>Argument2</i> of the callback routine.


## Return Value

None

## Remarks

Driver writers <u>must not</u> call <b>ExNotifyCallback</b> for any of the system-defined callback objects listed in <b>ExCreateCallback</b>.

The system calls callback routines in order of their registration.

For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>.

Callers of this routine must be running at IRQL &lt;= DISPATCH_LEVEL. The system calls all registered callback routines at the caller's IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a>

<a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExNotifyCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>