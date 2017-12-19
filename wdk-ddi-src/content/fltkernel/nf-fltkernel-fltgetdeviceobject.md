---
UID: NF.fltkernel.FltGetDeviceObject
title: FltGetDeviceObject function
author: windows-driver-content
description: The FltGetDeviceObject routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume.
old-location: ifsk\fltgetdeviceobject.htm
old-project: ifsk
ms.assetid: 1351efd1-1f7f-4f4b-b0ce-d9f08fba6613
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltGetDeviceObject
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
req.alt-api: FltGetDeviceObject
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

# FltGetDeviceObject function



## -description
The <b>FltGetDeviceObject</b> routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume. 



## -syntax

````
NTSTATUS FltGetDeviceObject(
  _In_  PFLT_VOLUME    Volume,
  _Out_ PDEVICE_OBJECT *DeviceObject
);
````


## -parameters

### -param Volume [in]

Opaque pointer for the volume. 


### -param DeviceObject [out]

Pointer to a caller-allocated variable that receives the volume device object pointer. This parameter is required and cannot be <b>NULL</b>. 


## -returns
<b>FltGetDeviceObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_FLT_NO_DEVICE_OBJECT</b></dt>
</dl>The requested device object does not exist for the given volume. This is an error code. 

 


## -remarks
<b>FltGetDeviceObject</b> returns a pointer to the Filter Manager's volume device object (VDO) for the given volume. 

For more information about volume device objects, see <a href="ifsk.file_system_stacks">File System Stacks</a>. 

The Filter Manager's VDO is not the same as the underlying storage driver's disk device object or the base file system's VDO. To get a pointer to the disk device object, call <a href="ifsk.fltgetdiskdeviceobject">FltGetDiskDeviceObject</a> on the volume specified in the <i>Volume</i> parameter. To get a pointer to the base file system's VDO, call <a href="ifsk.iogetdeviceattachmentbaseref">IoGetDeviceAttachmentBaseRef</a> on the <i>RetDeviceObject</i> returned by <b>FltGetDeviceObject</b>. 

To get an opaque pointer for the corresponding volume for a given device object, call <a href="ifsk.fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>. 

<b>FltGetDeviceObject</b> increments the reference count on the returned device object pointer. When this pointer is no longer needed, the caller must decrement this reference count by calling <a href="kernel.obdereferenceobject">ObDereferenceObject</a>. Thus every successful call to <b>FltGetDeviceObject</b> must be matched by a subsequent call to <b>ObDereferenceObject</b>. 


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
<a href="ifsk.fltgetdiskdeviceobject">FltGetDiskDeviceObject</a>
</dt>
<dt>
<a href="ifsk.fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>
</dt>
<dt>
<a href="ifsk.iogetdeviceattachmentbaseref">IoGetDeviceAttachmentBaseRef</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetDeviceObject routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

