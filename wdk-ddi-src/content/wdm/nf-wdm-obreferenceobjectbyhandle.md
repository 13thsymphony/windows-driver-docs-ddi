---
UID: NF:wdm.ObReferenceObjectByHandle
title: ObReferenceObjectByHandle function
author: windows-driver-content
description: The ObReferenceObjectByHandle routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body.
old-location: kernel\obreferenceobjectbyhandle.htm
old-project: kernel
ms.assetid: 6397d96e-f3b1-4e2f-91ce-b123c9e8de81
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ObReferenceObjectByHandle, ObReferenceObjectByHandle routine [Kernel-Mode Driver Architecture], k107_97ce2cea-8f20-4b30-996c-9ea268951aef.xml, kernel.obreferenceobjectbyhandle, wdm/ObReferenceObjectByHandle
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
req.ddi-compliance: IrqlObPassive, TargetRelationNeedsRef, HwStorPortProhibitedDDIs
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
-	ObReferenceObjectByHandle
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ObReferenceObjectByHandle function
The <b>ObReferenceObjectByHandle</b> routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body.

## Syntax

````
NTSTATUS ObReferenceObjectByHandle(
  _In_      HANDLE                     Handle,
  _In_      ACCESS_MASK                DesiredAccess,
  _In_opt_  POBJECT_TYPE               ObjectType,
  _In_      KPROCESSOR_MODE            AccessMode,
  _Out_     PVOID                      *Object,
  _Out_opt_ POBJECT_HANDLE_INFORMATION HandleInformation
);
````

## Parameters

`Handle`

Specifies an open handle for an object.

`DesiredAccess`

Specifies the requested types of access to the object. The interpretation of this field is dependent on the object type. Do not use any generic access rights. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.

`ObjectType`

Pointer to the object type. <i>ObjectType</i> can be <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsProcessType</b>, <b>*PsThreadType</b>, <b>*SeTokenObjectType</b>, <b>*TmEnlistmentObjectType</b>, <b>*TmResourceManagerObjectType</b>, <b>*TmTransactionManagerObjectType</b>, or <b>*TmTransactionObjectType</b>.

<div class="alert"><b>Note</b>  The <b>SeTokenObjectType</b> object type is supported starting with Windows XP.</div>
<div> </div>
If <i>ObjectType</i> is not <b>NULL</b>, the operating system verifies that the supplied object type matches the object type of the object that <i>Handle</i> specifies.

`AccessMode`

Specifies the access mode to use for the access check. It must be either <b>UserMode</b> or <b>KernelMode</b>. Drivers should always specify <b>UserMode</b> for handles they receive from user address space.

`Object`

Pointer to a variable that receives a pointer to the object's body. The following table contains the pointer types.

<table>
<tr>
<th><i>ObjectType</i> parameter</th>
<th><i>Object </i>pointer type</th>
</tr>
<tr>
<td>
<b>*ExEventObjectType</b>

</td>
<td>
PKEVENT

</td>
</tr>
<tr>
<td>
<b>*ExSemaphoreObjectType</b>

</td>
<td>
PKSEMAPHORE

</td>
</tr>
<tr>
<td>
<b>*IoFileObjectType</b>

</td>
<td>
PFILE_OBJECT

</td>
</tr>
<tr>
<td>
<b>*PsProcessType</b>

</td>
<td>
PEPROCESS or PKPROCESS

</td>
</tr>
<tr>
<td>
<b>*PsThreadType</b>

</td>
<td>
PETHREAD or PKTHREAD

</td>
</tr>
<tr>
<td>
<b>*SeTokenObjectType</b>

</td>
<td>
PACCESS_TOKEN

</td>
</tr>
<tr>
<td>
<b>*TmEnlistmentObjectType</b>

</td>
<td>
PKENLISTMENT

</td>
</tr>
<tr>
<td>
<b>*TmResourceManagerObjectType</b>

</td>
<td>
PKRESOURCEMANAGER

</td>
</tr>
<tr>
<td>
<b>*TmTransactionManagerObjectType</b>

</td>
<td>
PKTM

</td>
</tr>
<tr>
<td>
<b>*TmTransactionObjectType</b>

</td>
<td>
PKTRANSACTION

</td>
</tr>
</table>
 

The structures that the pointer types reference are opaque, and drivers cannot access the structure members. Because the structures are opaque, PEPROCESS is equivalent to PKPROCESS, and PETHREAD is equivalent to PKTHREAD.

<div class="alert"><b>Note</b>  The <b>SeTokenObjectType</b> object type is supported starting with Windows XP.</div>
<div> </div>

`HandleInformation`

Drivers set this to <b>NULL</b>.


## Return Value

<b>ObReferenceObjectByHandle</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectType</i> parameter specifies the wrong object type for the object that is identified by the <i>Handle</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot be granted the requested access rights to the object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The <i>Handle</i> parameter is not a valid object handle.

</td>
</tr>
</table>

## Remarks

A pointer to the object body is retrieved from the object table entry and returned to the caller by means of the <i>Object</i> parameter.

If <i>AccessMode</i> is <b>UserMode</b>, the requested access is compared to the granted access for the object. If <i>AccessMode</i> is <b>KernelMode</b>, the handle should originate in the kernel address space.

Starting with Windows 7, if <i>AccessMode</i> is <b>KernelMode</b> and handle is received from user address space, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> issues bugcheck C4, subcode F6.

If the call succeeds, a pointer to the object body is returned to the caller and the pointer reference count is incremented. Incrementing this count prevents the object from being deleted while the pointer is being referenced. The caller must decrement the reference count with <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> as soon as it is done with the object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlObPassive, TargetRelationNeedsRef, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a>



<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>