---
UID: NF:ntifs.PsLookupThreadByThreadId
title: PsLookupThreadByThreadId function
author: windows-driver-content
description: The PsLookupThreadByThreadId routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.
old-location: ifsk\pslookupthreadbythreadid.htm
old-project: ifsk
ms.assetid: 4b61f480-6432-48db-9211-68a7d823d698
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsLookupThreadByThreadId, PsLookupThreadByThreadId routine [Installable File System Drivers], ifsk.pslookupthreadbythreadid, ntifs/PsLookupThreadByThreadId, psref_36f0c499-8370-4257-849c-dc8bad2720cc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	PsLookupThreadByThreadId
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsLookupThreadByThreadId function
The <b>PsLookupThreadByThreadId</b> routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.

## Syntax

```
NTKERNELAPI NTSTATUS PsLookupThreadByThreadId(
  HANDLE   ThreadId,
  PETHREAD *Thread
);
```

## Parameters

`ThreadId`

Specifies the thread ID of the thread.

`Thread`

Returns a referenced pointer to the ETHREAD structure of thread specified by the <i>ThreadId</i>.


## Return Value

<b>PsLookupThreadByThreadId </b>returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The thread ID was not found.

</td>
</tr>
</table>

## Remarks

This routine is available on Windows 2000 and later versions. 

If the call to <b>PsLookupThreadByThreadId</b> is successful, <b>PsLookupThreadByThreadId</b> increases the reference count on the object returned in the <i>Thread</i> parameter. Consequently, when a driver has completed using the <i>Thread</i> parameter, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> to dereference the <i>Thread</i> parameter received from the <b>PsLookupThreadByThreadId</b> routine. 

The ETHREAD structure is an opaque data structure used internally by the operating system. This structure can be passed to other routines to access specific information in this structure.

A file system filter driver can enumerate active threads by calling <b>PsLookupThreadByThreadId</b> to convert a thread ID to an ETHREAD structure. The thread ID is available in the thread create routine. A file system filter driver can set a thread notification callback routine using <a href="https://msdn.microsoft.com/library/windows/hardware/ff559954">PsSetCreateThreadNotifyRoutine</a>. In the notification callback routine, the file system filter driver can use the passed in <i>ThreadId</i> parameter and call <b>PsLookupThreadByThreadId </b>to locate the ETHREAD structure.

The <b>PsLookupThreadByThreadId</b> routine contains pageable code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559935">PsGetCurrentProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559937">PsGetCurrentThreadId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551920">PsLookupProcessByProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559947">PsRemoveCreateThreadNotifyRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559949">PsRemoveLoadImageNotifyRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559954">PsSetCreateThreadNotifyRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a>