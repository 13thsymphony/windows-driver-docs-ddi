---
UID: NF.ntifs.IoGetLowerDeviceObject
title: IoGetLowerDeviceObject function
author: windows-driver-content
description: The IoGetLowerDeviceObject routine returns a pointer to the next-lower-level device object on the driver stack.
old-location: ifsk\iogetlowerdeviceobject.htm
old-project: ifsk
ms.assetid: 2446dfee-baa4-4f7b-a5a0-ff13bf45ce4b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IoGetLowerDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetLowerDeviceObject
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

# IoGetLowerDeviceObject function



## -description
The <b>IoGetLowerDeviceObject</b> routine returns a pointer to the next-lower-level device object on the driver stack.



## -syntax

````
PDEVICE_OBJECT IoGetLowerDeviceObject(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param DeviceObject [in]

A pointer to the device object in the stack for which the next-lower-level device object is to be returned. 


## -returns
<b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the driver stack. 


## -remarks
Given a pointer to a device object in a file system or device driver stack, <b>IoGetLowerDeviceObject</b> returns a pointer to the next-lower-level device object on the stack.

<b>IoGetLowerDeviceObject</b> returns <b>NULL</b> if: 

The next-lower-level driver is not loaded. 

The next-lower-level driver is currently being unloaded, removed, or deleted. 

The device object pointed to by <i>DeviceObject</i> is the lowest device object in the driver stack. 

A file system filter driver typically uses <b>IoGetLowerDeviceObject</b> to determine whether it is already attached to the filter driver stack that is chained above a given file system device object. First, the filter calls <a href="kernel.iogetattacheddevicereference">IoGetAttachedDeviceReference</a> to get a pointer to the topmost device object in the stack. Then it calls <b>IoGetLowerDeviceObject</b> repeatedly to walk the driver stack, checking each device object to see whether the object belongs to the filter driver. 

<b>IoGetLowerDeviceObject</b> increments the reference count on the next-lower-level device object. Thus every successful call to <b>IoGetLowerDeviceObject</b> must be matched by a subsequent call <a href="kernel.obdereferenceobject">ObDereferenceObject</a>. 


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
This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later. 

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
<a href="ifsk.iogetattacheddevice">IoGetAttachedDevice</a>
</dt>
<dt>
<a href="kernel.iogetattacheddevicereference">IoGetAttachedDeviceReference</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetLowerDeviceObject routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

