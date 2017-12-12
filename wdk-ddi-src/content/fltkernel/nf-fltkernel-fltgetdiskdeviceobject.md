---
UID: NF.fltkernel.FltGetDiskDeviceObject
title: FltGetDiskDeviceObject function
author: windows-driver-content
description: The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume.
old-location: ifsk\fltgetdiskdeviceobject.htm
old-project: ifsk
ms.assetid: fb85aa34-5983-405b-85d3-7ebc4be49c51
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltGetDiskDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetDiskDeviceObject
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
---

# FltGetDiskDeviceObject function



## -description
The <b>FltGetDiskDeviceObject</b> routine returns a pointer to the disk device object associated with a given volume. 



## -syntax

````
NTSTATUS FltGetDiskDeviceObject(
  _In_  PFLT_VOLUME    Volume,
  _Out_ PDEVICE_OBJECT *DiskDeviceObject
);
````


## -parameters

### -param Volume [in]

Opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param DiskDeviceObject [out]

Pointer to a caller-allocated variable that receives the device object pointer. This parameter is required and cannot be <b>NULL</b>. 


## -returns
<b>FltGetDiskDeviceObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_FLT_NO_DEVICE_OBJECT</b></dt>
</dl>The requested device object does not exist for the given volume. This is an error code. 

 


## -remarks
<b>FltGetDiskDeviceObject</b> retrieves a pointer to the storage device object for the physical disk where the volume resides. The storage device need not be an actual disk. 

<b>FltGetDiskDeviceObject</b> increments the reference count on the device object pointer returned in *<i>DiskDeviceObject</i>. When this pointer is no longer needed, the caller must decrement this reference count by calling <a href="kernel.obdereferenceobject">ObDereferenceObject</a>. Failure to do so prevents the system from freeing or deleting the device object because of the outstanding reference. Thus every successful call to <b>FltGetDiskDeviceObject</b> must be matched by a subsequent call to <b>ObDereferenceObject</b>. 

A minifilter must call <b>FltGetDiskDeviceObject</b> only in an I/O related   callback. Otherwise, the fields of the device object returned may not be valid. This the case in callback routines such as <a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">InstanceTeardownStartCallback</a> and <b>InstanceTeardownCompleteCallback</b>.

To get a pointer to the Filter Manager's volume device object (VDO) for a given volume, call <a href="ifsk.fltgetdeviceobject">FltGetDeviceObject</a>. 

To get an opaque volume pointer for the volume represented by a volume device object, call <a href="ifsk.fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>. 

For more information about volume device objects, see <a href="ifsk.file_system_stacks">File System Stacks</a>. 


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
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fltmgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltgetdeviceobject">FltGetDeviceObject</a>
</dt>
<dt>
<a href="ifsk.fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetDiskDeviceObject routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

