---
UID: NF.wdm.ObReferenceObjectByPointer
title: ObReferenceObjectByPointer function
author: windows-driver-content
description: The ObReferenceObjectByPointer routine increments the pointer reference count for a given object.
old-location: kernel\obreferenceobjectbypointer.htm
old-project: kernel
ms.assetid: c575bd3f-6790-4815-b7c7-8ee16a9cac17
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ObReferenceObjectByPointer
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
req.alt-api: ObReferenceObjectByPointer
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: TargetRelationNeedsRef, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# ObReferenceObjectByPointer function



## -description
The <b>ObReferenceObjectByPointer</b> routine increments the pointer reference count for a given object.



## -syntax

````
NTSTATUS ObReferenceObjectByPointer(
  _In_     PVOID           Object,
  _In_     ACCESS_MASK     DesiredAccess,
  _In_opt_ POBJECT_TYPE    ObjectType,
  _In_     KPROCESSOR_MODE AccessMode
);
````


## -parameters

### -param Object [in]

Pointer to the object's body.


### -param DesiredAccess [in]

Specifies a mask representing the requested access to the object.


### -param ObjectType [in, optional]

Pointer to the object type. <i>ObjectType</i> can be <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsProcessType</b>, <b>*PsThreadType</b>, <b>*SeTokenObjectType</b>, <b>*TmEnlistmentObjectType</b>, <b>*TmResourceManagerObjectType</b>, <b>*TmTransactionManagerObjectType</b>, or <b>*TmTransactionObjectType</b>. 

<div class="alert"><b>Note</b>    The <b>SeTokenObjectType</b> object type is supported in Windows XP and later versions of Windows.</div>
<div> </div>
This parameter can also be <b>NULL</b> if <i>AccessMode</i> is <b>KernelMode</b>.


### -param AccessMode [in]

Indicates the access mode to use for the access check. It must be either <b>UserMode</b> or <b>KernelMode</b>. Lower-level drivers should specify <b>KernelMode</b>.


## -returns
<b>ObReferenceObjectByPointer</b> returns an NTSTATUS value. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>

## -remarks
Calling this routine prevents the object from being deleted, possibly by another component's call to <a href="kernel.obdereferenceobject">ObDereferenceObject</a> or <a href="kernel.zwclose">ZwClose</a>. The caller must decrement the reference count with <b>ObDereferenceObject</b> as soon as it is done with the object.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_targetrelationneedsref">TargetRelationNeedsRef</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
<dt>
<a href="kernel.obreferenceobject">ObReferenceObject</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectByPointer routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

