---
UID: NF.ntifs.IoCreateStreamFileObject
title: IoCreateStreamFileObject function
author: windows-driver-content
description: The IoCreateStreamFileObject routine creates a new stream file object.
old-location: ifsk\iocreatestreamfileobject.htm
old-project: ifsk
ms.assetid: 4186a362-f75d-4633-b9eb-5b0810bf56dc
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IoCreateStreamFileObject
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
req.alt-api: IoCreateStreamFileObject
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
req.irql: <= DISPATCH_LEVEL
---

# IoCreateStreamFileObject function



## -description
The <b>IoCreateStreamFileObject</b> routine creates a new stream file object. 



## -syntax

````
PFILE_OBJECT IoCreateStreamFileObject(
  _In_opt_ PFILE_OBJECT   FileObject,
  _In_opt_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param FileObject [in, optional]

Pointer to the file object to which the new stream file is related. This parameter is optional and can be <b>NULL</b>. 


### -param DeviceObject [in, optional]

Pointer to a device object for the device on which the stream file is to be opened. If the caller specifies a non-<b>NULL</b> value for <i>FileObject</i>, the value of <i>DeviceObject</i> is ignored. Otherwise, the caller must specify a non-<b>NULL</b> value for <i>DeviceObject</i>. 


## -returns
<b>IoCreateStreamFileObject</b> returns a pointer to the newly created stream file object.


## -remarks
File systems call <b>IoCreateStreamFileObject</b> to create a new stream file object. A <i>stream file object</i> is identical to an ordinary file object, except that the FO_STREAM_FILE file object flag is set. 

A stream file object is commonly used to represent an internal stream for a volume mounted by the file system. This <i>virtual volume file</i> permits the file system to view, change, and cache the volume's on-disk structure as if it were an ordinary file. In this case, the <i>DeviceObject</i> parameter in the call to <b>IoCreateStreamFileObject</b> specifies the volume device object (VDO) for the volume. 

A stream file object can also be used to represent an alternate data stream for accessing a file's metadata, such as extended attributes or security descriptors. In this case, the <i>FileObject</i> parameter in the call to <b>IoCreateStreamFileObject</b> specifies an existing file object for the file. The newly created stream file object permits the file system to view, change, and cache the file's metadata as if it were an ordinary file. 

When the stream file object is no longer needed, the caller must decrement its reference count by calling <a href="kernel.obdereferenceobject">ObDereferenceObject</a>. When the stream file object's reference count reaches zero, an IRP_MJ_CLOSE request is sent to the file system driver stack for the volume. 

File system filter driver writers should note that <b>IoCreateStreamFileObject</b> causes an IRP_MJ_CLEANUP request to be sent to the file system driver stack for the volume. Because file systems often create stream file objects as a side effect of operations other than IRP_MJ_CREATE, it is difficult for filter drivers to reliably detect stream file object creation. Thus a filter driver should expect to receive IRP_MJ_CLEANUP and IRP_MJ_CLOSE requests for previously unseen file objects. 

If a pool allocation failure occurs, <b>IoCreateStreamFileObject</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. 


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.iocreatestreamfileobjectex">IoCreateStreamFileObjectEx</a>
</dt>
<dt>
<a href="ifsk.iocreatestreamfileobjectlite">IoCreateStreamFileObjectLite</a>
</dt>
<dt>
<a href="ifsk.irp_mj_cleanup">IRP_MJ_CLEANUP</a>
</dt>
<dt>
<a href="ifsk.irp_mj_close">IRP_MJ_CLOSE</a>
</dt>
<dt>
<a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCreateStreamFileObject routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

