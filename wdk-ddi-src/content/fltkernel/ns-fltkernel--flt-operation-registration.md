---
UID: NS.fltkernel._FLT_OPERATION_REGISTRATION
title: FLT_OPERATION_REGISTRATION
author: windows-driver-content
description: The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines.
old-location: ifsk\flt_operation_registration.htm
old-project: ifsk
ms.assetid: 5e3f9a29-660e-46f1-bf25-5bad8b91e32c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FLT_OPERATION_REGISTRATION, FLT_OPERATION_REGISTRATION, *PFLT_OPERATION_REGISTRATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FLT_OPERATION_REGISTRATION
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# FLT_OPERATION_REGISTRATION structure



## -description
<p>The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines. </p>


## -syntax

````
typedef struct _FLT_OPERATION_REGISTRATION {
  UCHAR                            MajorFunction;
  FLT_OPERATION_REGISTRATION_FLAGS Flags;
  PFLT_PRE_OPERATION_CALLBACK      PreOperation;
  PFLT_POST_OPERATION_CALLBACK     PostOperation;
  PVOID                            Reserved1;
} FLT_OPERATION_REGISTRATION, *PFLT_OPERATION_REGISTRATION;
````


## -struct-fields
<dl>

### -field <b>MajorFunction</b>

<dd>
<p>Major function code specifying the type of I/O operation. This member is required and cannot be <b>NULL</b>. For more information about additional operations, see <a href="..\fltkernel\ns-fltkernel--flt-parameters.md">FLT_PARAMETERS</a>.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Bitmask of flags specifying when to call the preoperation (<a href="..\fltkernel\nc-fltkernel-pflt-pre-operation-callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) and postoperation (<a href="..\fltkernel\nc-fltkernel-pflt-post-operation-callback.md">PFLT_POST_OPERATION_CALLBACK</a>) callback routines for cached I/O or paging I/O operations. This member is optional and can be zero. </p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>FLTFL_OPERATION_REGISTRATION_SKIP_CACHED_IO</p>
</td>
<td>
<p>A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for cached I/O operations. This flag applies to fast I/O as well as IRP-based reads and writes because all fast I/O is cached. </p>
</td>
</tr>
<tr>
<td>
<p>FLTFL_OPERATION_REGISTRATION_SKIP_PAGING_IO</p>
</td>
<td>
<p>A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for paging I/O operations. This flag applies only to IRP-based I/O operations. It is ignored for I/O operations that are not IRP-based. </p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>PreOperation</b>

<dd>
<p>Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt-pre-operation-callback.md">PFLT_PRE_OPERATION_CALLBACK</a>-typed routine to be registered as the preoperation callback routine for this type of I/O operation. This member is optional and can be <b>NULL</b>. </p>
</dd>

### -field <b>PostOperation</b>

<dd>
<p>Pointer to a <a href="..\fltkernel\nc-fltkernel-pflt-post-operation-callback.md">PFLT_POST_OPERATION_CALLBACK</a>-typed routine to be registered as the postoperation callback routine for this type of I/O operation. This member is optional and can be <b>NULL</b>. </p>
</dd>

### -field <b>Reserved1</b>

<dd>
<p>Reserved for system use. Minifilters must set this member to <b>NULL</b>. </p>
</dd>
</dl>

## -remarks
<p>When a minifilter calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <b>DriverEntry</b> routine, it can register a preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt-pre-operation-callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine and a postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt-post-operation-callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine for each type of I/O operation that it must handle. </p>

<p>To register these callback routines, the minifilter creates a variable-length array of FLT_OPERATION_REGISTRATION structures and stores a pointer to the array in the <b>OperationRegistration</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-registration.md">FLT_REGISTRATION</a> structure that the minifilter passes as the <i>Registration</i> parameter of <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. The last element of this array must be {IRP_MJ_OPERATION_END}. </p>

<p>The minifilter must create a separate FLT_OPERATION_REGISTRATION structure for each type of I/O operation that it handles. In this structure, the minifilter specifies the entry points of its callback routines in the structure's <b>PreOperation</b> and <b>PostOperation</b> members. </p>

<p>A minifilter can register a preoperation callback routine for a given type of I/O operation without registering a postoperation callback and vice versa. </p>

<p>File systems do not receive IRP_MJ_POWER or IRP_MJ_DEVICE_CHANGE requests. Minifilters cannot register preoperation or postoperation callback routines for these operations. </p>

<p>A minifilter cannot register a postoperation callback routine for IRP_MJ_SHUTDOWN. </p>

<p>A single preoperation or postoperation callback routine can be used to process more than one type of I/O operation. However, the callback routine must be registered separately for each type of I/O operation. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-registration.md">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt-post-operation-callback.md">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt-pre-operation-callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_OPERATION_REGISTRATION structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
