---
UID : NF:ntifs.PsLookupThreadByThreadId
title : PsLookupThreadByThreadId function
author : windows-driver-content
description : The PsLookupThreadByThreadId routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.
old-location : ifsk\pslookupthreadbythreadid.htm
old-project : ifsk
ms.assetid : 4b61f480-6432-48db-9211-68a7d823d698
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PsLookupThreadByThreadId routine [Installable File System Drivers], PsLookupThreadByThreadId, ifsk.pslookupthreadbythreadid, ntifs/PsLookupThreadByThreadId, psref_36f0c499-8370-4257-849c-dc8bad2720cc.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
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
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= APC_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# PsLookupThreadByThreadId function
The <b>PsLookupThreadByThreadId</b> routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.

## Syntax

````
NTSTATUS PsLookupThreadByThreadId(
  _In_  HANDLE   ThreadId,
  _Out_ PETHREAD *Thread
);
````

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

If the call to <b>PsLookupThreadByThreadId</b> is successful, <b>PsLookupThreadByThreadId</b> increases the reference count on the object returned in the <i>Thread</i> parameter. Consequently, when a driver has completed using the <i>Thread</i> parameter, the driver must call <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> to dereference the <i>Thread</i> parameter received from the <b>PsLookupThreadByThreadId</b> routine. 

The ETHREAD structure is an opaque data structure used internally by the operating system. This structure can be passed to other routines to access specific information in this structure.

A file system filter driver can enumerate active threads by calling <b>PsLookupThreadByThreadId</b> to convert a thread ID to an ETHREAD structure. The thread ID is available in the thread create routine. A file system filter driver can set a thread notification callback routine using <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>. In the notification callback routine, the file system filter driver can use the passed in <i>ThreadId</i> parameter and call <b>PsLookupThreadByThreadId </b>to locate the ETHREAD structure.

The <b>PsLookupThreadByThreadId</b> routine contains pageable code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\nf-ntifs-pslookupprocessbyprocessid.md">PsLookupProcessByProcessId</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>

<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>

<a href="..\ntddk\nf-ntddk-psgetcurrentthreadid.md">PsGetCurrentThreadId</a>

<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>

<a href="..\ntddk\nf-ntddk-psremoveloadimagenotifyroutine.md">PsRemoveLoadImageNotifyRoutine</a>

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>

<a href="..\ntddk\nf-ntddk-psremovecreatethreadnotifyroutine.md">PsRemoveCreateThreadNotifyRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsLookupThreadByThreadId routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>