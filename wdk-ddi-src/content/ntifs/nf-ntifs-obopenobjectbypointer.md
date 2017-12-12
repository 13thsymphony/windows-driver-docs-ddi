---
UID: NF.ntifs.ObOpenObjectByPointer
title: ObOpenObjectByPointer function
author: windows-driver-content
description: The ObOpenObjectByPointer function opens an object referenced by a pointer and returns a handle to the object.
old-location: ifsk\obopenobjectbypointer.htm
old-project: ifsk
ms.assetid: f2aa198e-6018-486f-8c39-c89c3f78cb41
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ObOpenObjectByPointer
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
req.alt-api: ObOpenObjectByPointer
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# ObOpenObjectByPointer function



## -description

   The <b>ObOpenObjectByPointer</b> function opens an object referenced by a pointer and returns a handle to the object. 



## -syntax

````
NTSTATUS ObOpenObjectByPointer(
  _In_     PVOID           Object,
  _In_     ULONG           HandleAttributes,
  _In_opt_ PACCESS_STATE   PassedAccessState,
  _In_     ACCESS_MASK     DesiredAccess,
  _In_opt_ POBJECT_TYPE    ObjectType,
  _In_     KPROCESSOR_MODE AccessMode,
  _Out_    PHANDLE         Handle
);
````


## -parameters

### -param Object [in]

Pointer to the object to be opened. 


### -param HandleAttributes [in]

Bitmask of flags specifying the desired attributes for the object handle. If the caller is not running in the system process context, these flags must include OBJ_KERNEL_HANDLE. This parameter is optional and can be zero. Otherwise, it is an ORed combination of one or more of the following: 


### -param OBJ_EXCLUSIVE

<dd>
The object is to be opened for exclusive access. If this flag is set and the call to <b>ObOpenObjectByPointer</b> succeeds, the object cannot be shared and cannot be opened again until the handle is closed. This flag is incompatible with the OBJ_INHERIT flag. This flag is invalid for file objects. 


### -param OBJ_FORCE_ACCESS_CHECK

<dd>
All access checks are to be enforced for the object, even if the object is being opened in kernel mode. If this flag is specified, the value of the <i>AccessMode</i> parameter is ignored. 


### -param OBJ_INHERIT

<dd>
The handle can be inherited by child processes of the current process. This flag is incompatible with the OBJ_EXCLUSIVE flag. 


### -param OBJ_KERNEL_HANDLE

<dd>
The handle can only be accessed in kernel mode. This flag must be specified if the caller is not running in the system process context. 

</dd>
</dl>

### -param PassedAccessState [in, optional]

Pointer to an <a href="ifsk.access_state">ACCESS_STATE</a> structure containing the object's subject context, granted access types, and remaining desired access types. This parameter is optional and can be <b>NULL</b>. In a create dispatch routine, this pointer can be found in <i>IrpSp-&gt;Parameters.Create.SecurityContext-&gt;AccessState</i>, where <b>IrpSp</b> is a pointer to the caller's own stack location in the IRP. (For more information, see <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>.) 


### -param DesiredAccess [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value specifying the desired access to the object. This parameter is optional and can be zero. 


### -param ObjectType [in, optional]

Pointer to the object type. If the value of <i>AccessMode</i> is <b>KernelMode</b>, this parameter is optional and can be <b>NULL</b>. Otherwise, it must be either <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsThreadType </b>, <b>*SeTokenObjectType</b>, or <b>*CmKeyObjectType</b>. 

<div class="alert"><b>Note</b>    The <b>SeTokenObjectType</b> object type is supported staring with Windows XP and  and the <b>CmKeyObjectType</b> object type is supported staring with Windows 7.</div>
<div> </div>

### -param AccessMode [in]

Access mode to be used for the access check. This parameter is required and must be either <b>UserMode</b> or <b>KernelMode</b>. 


### -param Handle [out]

Pointer to a caller-allocated variable that receives a handle to the object. 


## -returns
<b>ObOpenObjectByPointer</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required access to open a handle for the object. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>ObOpenObjectByPointer</b> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid flag value was specified in the <i>HandleAttributes</i> parameter. This is an error code. 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The object pointed to by the <i>Object</i> parameter was not of the type specified in the <i>ObjectType</i> parameter. This is an error code. 
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>The caller did not have the required privilege to create a handle with the access specified in the <i>DesiredAccess</i> parameter. This is an error code. 
<dl>
<dt><b>STATUS_QUOTA_EXCEEDED</b></dt>
</dl>The caller is running in the context of a process whose memory quota is not sufficient to allocate the object handle. This is an error code. 
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The object handle could not be created. This is an error code. 

 


## -remarks
If the <i>Object</i> parameter points to a file object (that is, a FILE_OBJECT structure), <b>ObOpenObjectByPointer</b> can only be called after at least one handle has been created for the file object. Callers can check the <b>Flags</b> member of the FILE_OBJECT structure that the <i>Object</i> parameter points to. If the FO_HANDLE_CREATED flag is set, this means that one or more handles have been created for the file object, so it is safe to call <b>ObOpenObjectByPointer</b>. 

Any handle obtained by calling <b>ObOpenObjectByPointer</b> must eventually be released by calling <a href="kernel.zwclose">ZwClose</a>. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE flag in the <i>HandleAttributes</i> parameter. This restricts the use of the handle returned by <b>ObOpenObjectByPointer</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

If the <i>AccessMode</i> parameter is <b>KernelMode</b>, the requested access is always allowed. If <i>AccessMode</i> is <b>UserMode</b>, the requested access is compared to the granted access for the object. 


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="ifsk.access_state">ACCESS_STATE</a>
</dt>
<dt>
<a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="kernel.obreferenceobject">ObReferenceObject</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbypointer">ObReferenceObjectByPointer</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ObOpenObjectByPointer function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

