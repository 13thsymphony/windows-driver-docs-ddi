---
UID: NF:wdm.IoGetAttachedDeviceReference
title: IoGetAttachedDeviceReference function
author: windows-driver-content
description: The IoGetAttachedDeviceReference routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.
old-location: kernel\iogetattacheddevicereference.htm
old-project: kernel
ms.assetid: 540a4e5c-8d7b-4ba8-a9a6-6e13d9b85f23
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetAttachedDeviceReference
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
req.alt-api: IoGetAttachedDeviceReference
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: DanglingDeviceObjectReference, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetAttachedDeviceReference function



## -description
The <b>IoGetAttachedDeviceReference</b> routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.



## -syntax

````
PDEVICE_OBJECT IoGetAttachedDeviceReference(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object for which the topmost attached device object is retrieved. 


## -returns
<b>IoGetAttachedDeviceReference</b> returns a pointer to the highest level device object in a stack of attached device objects after incrementing the reference count on the object.


## -remarks
If the device object at <i>DeviceObject</i> has no device objects attached to it, <i>DeviceObject</i> and the returned pointer are equal.

Device driver writers must ensure that when they have completed all operations that required them to make this call, that they call <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> with the device object pointer returned by this routine. Failure to do so will prevent the system from freeing or deleting the device object because of an outstanding reference count.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543619">DanglingDeviceObjectReference</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetAttachedDeviceReference routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

