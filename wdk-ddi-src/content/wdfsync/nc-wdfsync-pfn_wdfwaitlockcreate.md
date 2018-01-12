---
UID: NC:wdfsync.PFN_WDFWAITLOCKCREATE
title: PFN_WDFWAITLOCKCREATE function
author: windows-driver-content
description: The WdfWaitLockCreate method creates a framework wait-lock object.
old-location: wdf\wdfwaitlockcreate.htm
old-project: wdf
ms.assetid: a0ffa493-4490-440b-9f67-426a7b5d4442
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFWAITLOCKCREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfWaitLockCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ParentObjectCheckLock
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFWAITLOCKCREATE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWaitLockCreate</b> method creates a framework wait-lock object.



## -syntax

````
NTSTATUS WdfWaitLockCreate(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES LockAttributes,
  _Out_    WDFWAITLOCK            *Lock
);
````


## -parameters

### -param LockAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the wait-lock object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Lock [out]

A pointer to a location that receives a handle to a new framework wait-lock object.


## -returns
<b>WdfWaitLockCreate</b> returns STATUS_SUCCESS if the operation succeeds. 

For a list of other return values that the <b>WdfWaitLockCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The <b>WdfWaitLockCreate</b> method creates a framework wait-lock object. After creating a wait-lock object, a driver can call <a href="..\wdfsync\nf-wdfsync-wdfwaitlockacquire.md">WdfWaitLockAcquire</a> to acquire the lock and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556116">WdfWaitLockRelease</a> to release the lock.

By default, the new wait-lock object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the wait-lock object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the wait-lock object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about wait locks, see <a href="wdf.synchronization_techniques_for_wdf_drivers">Synchronization Techniques for Framework-Based Drivers</a>.

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>, specifies that the wait lock's parent object will be a device object, and calls <b>WdfWaitLockCreate</b>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfsync.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975095">ParentObjectCheckLock</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
<dt>
<a href="..\wdfsync\nf-wdfsync-wdfwaitlockacquire.md">WdfWaitLockAcquire</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556116">WdfWaitLockRelease</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWaitLockCreate method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

