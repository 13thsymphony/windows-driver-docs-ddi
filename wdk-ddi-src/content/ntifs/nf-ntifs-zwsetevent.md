---
UID: NF:ntifs.ZwSetEvent
title: ZwSetEvent function
author: windows-driver-content
description: The ZwSetEvent routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.
old-location: kernel\zwsetevent.htm
old-project: kernel
ms.assetid: f561fc3e-2233-4237-a88d-bd5a887a1e7a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: NtSetEvent, ZwSetEvent, ZwSetEvent routine [Kernel-Mode Driver Architecture], k111_e01bbbbf-29f9-4c0a-89a2-84cf927aeb47.xml, kernel.zwsetevent, ntifs/NtSetEvent, ntifs/ZwSetEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwSetEvent
-	NtSetEvent
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ZwSetEvent function
The <b>ZwSetEvent</b> routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.

## Syntax

```
NTSYSAPI NTSTATUS ZwSetEvent(
  HANDLE EventHandle,
  PLONG  PreviousState
);
```

## Parameters

`EventHandle`

A handle to an event object.

`PreviousState`

An optional pointer to a variable where the previous state of the event object is stored on output.


## Return Value

<b>ZwSetEvent</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required privileges to modify the event specified by the <i>EventHandle</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Resources required by this function could not be allocated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The supplied <i>EventHandle</i> parameter was invalid. 

</td>
</tr>
</table>

## Remarks

<b>ZwSetEvent</b> sets an event object to a Signaled state and attempts to satisfy as many waits as possible.

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetEvent</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557667">NtSetEvent</a>" instead of "<b>ZwSetEvent</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549039">IoCreateNotificationEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549045">IoCreateSynchronizationEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551980">KeClearEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553176">KeResetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553253">KeSetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566423">ZwCreateEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567120">ZwWaitForSingleObject</a>