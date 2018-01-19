---
UID : NF:ntifs.PsLookupProcessByProcessId
title : PsLookupProcessByProcessId function
author : windows-driver-content
description : The PsLookupProcessByProcessId routine accepts the process ID of a process and returns a referenced pointer to EPROCESS structure of the process.
old-location : ifsk\pslookupprocessbyprocessid.htm
old-project : ifsk
ms.assetid : f9c4bcab-5584-4b26-b4ff-6067d7ef1890
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PsLookupProcessByProcessId
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
req.alt-api : PsLookupProcessByProcessId
req.alt-loc : NtosKrnl.exe
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
req.typenames : TOKEN_TYPE
---


# PsLookupProcessByProcessId function
The <b>PsLookupProcessByProcessId</b> routine accepts the process ID of a process and returns a referenced pointer to EPROCESS structure of the process.

## Syntax

````
NTSTATUS PsLookupProcessByProcessId(
  _In_  HANDLE    ProcessId,
  _Out_ PEPROCESS *Process
);
````

## Parameters

`ProcessId`

Specifies the process ID of the process.

`Process`

Returns a referenced pointer to the EPROCESS structure of process specified by <i>ProcessId</i>.


## Return Value

<b>PsLookupProcessByProcessId </b>returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The process ID was not found.

## Remarks

This routine is available on Windows 2000 and later versions. 

If the call to <b>PsLookupProcessByProcessId</b> is successful, <b>PsLookupProcessByProcessID</b> increases the reference count on the object returned in the <i>Process</i> parameter. Consequently, when a driver has completed using the <i>Process</i> parameter, the driver must call <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> to dereference the <i>Process</i> parameter received from the <b>PsLookupProcessByProcessID</b> routine. 

The EPROCESS structure is an opaque data structure used internally by the operating system. This structure can be passed to other routines to access specific information in this structure.

A file system filter driver can enumerate active processes and then call <b>PsLookupProcessByProcessId</b> to convert a process ID to an EPROCESS structure. The process ID is available in the process create routine. A file system filter driver can set a process notification callback routine using <a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>. In the notification callback routine, the file system filter driver can use the passed in <i>ProcessId</i> parameter and call <b>PsLookupProcessByProcessID </b>to locate the EPROCESS structure. The <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a> can also be used to set a notification routine that returns the process ID when a thread ID is created.

The <b>PsLookupProcessByProcessId</b> routine contains pageable code.

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

<dl>
<dt>
<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentthreadid.md">PsGetCurrentThreadId</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-pslookupthreadbythreadid.md">PsLookupThreadByThreadId</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psremovecreatethreadnotifyroutine.md">PsRemoveCreateThreadNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psremoveloadimagenotifyroutine.md">PsRemoveLoadImageNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsLookupProcessByProcessId routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>