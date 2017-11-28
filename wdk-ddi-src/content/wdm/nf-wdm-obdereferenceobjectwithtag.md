---
UID: NF.wdm.ObDereferenceObjectWithTag
title: ObDereferenceObjectWithTag
author: windows-driver-content
description: The ObDereferenceObjectWithTag routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obdereferenceobjectwithtag.htm
old-project: kernel
ms.assetid: 872098c1-d684-4ce5-9f53-2fee8b50b626
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ObDereferenceObjectWithTag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObDereferenceObjectWithTag
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ObDereferenceObjectWithTag function



## -description
<p>The <b>ObDereferenceObjectWithTag</b> routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>. </p>


## -syntax

````
VOID ObDereferenceObjectWithTag(
  _In_ PVOID Object,
  _In_ ULONG Tag
);
````


## -parameters
<dl>

### -param <i>Object</i> [in]

<dd>
<p>A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558683">ObReferenceObjectByHandleWithTag</a> routine after it opens the object. </p>
</dd>

### -param <i>Tag</i> [in]

<dd>
<p>Specifies a four-byte, custom tag value. For more information, see the following Remarks section. </p>
</dd>
</dl>

## -returns
<p><b>ObDereferenceObjectWithTag</b> returns a value that is reserved for system use. Drivers must treat this value as VOID. </p>

## -remarks
<p>A kernel-mode driver calls this routine to decrement the reference count of an object by one. If the object was created as <i>temporary</i> (that is, the OBJ_PERMANENT flag was not specified when the object was created), and the reference count reaches zero, the object manager deletes the object.</p>

<p>When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.</p>

<p>An object is <i>permanent</i> if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>.) A permanent object is created with an initial reference count of one, so the object is not deleted when the driver removes its last reference to the object.</p>

<p>To prepare a permanent object to be deleted, a driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566477">ZwMakeTemporaryObject</a> routine to make the object temporary. A driver should only delete a permanent object that it created. Use the following steps to delete a permanent object:</p>

<p>Call <b>ObDereferenceObjectWithTag</b>. </p>

<p>Get the handle to the object. If necessary, call the appropriate <b>ZwOpen<i>Xxx</i></b> or <b>ZwCreate<i>Xxx</i></b> routine to get the object handle.</p>

<p>Call <b>ZwMakeTemporaryObject</b> with the handle obtained in step 2. </p>

<p>Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> with the handle obtained in step 2.</p>

<p>If the immediate deletion of an object by the current thread might cause a deadlock, do not call <b>ObDereferenceObjectWithTag</b> to dereference the object. Instead, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557732">ObDereferenceObjectDeferDeleteWithTag</a> routine to dereference the object.</p>

<p>For example, such a deadlock can occur if <b>ObDereferenceObjectWithTag</b> is used to dereference a <a href="https://msdn.microsoft.com/43bf96ed-8be8-4670-a310-99cd7c7f9073">Kernel Transaction Manager</a> (KTM) object when a higher-level driver on the driver stack is holding a lock.</p>

<p>For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> routine is similar to <b>ObDereferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObDereferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObDereferenceObject</b> has the same effect as a call to <b>ObDereferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.</p>

<p>To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <b>!obtrace</b> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>. </p>

<p>A kernel-mode driver calls this routine to decrement the reference count of an object by one. If the object was created as <i>temporary</i> (that is, the OBJ_PERMANENT flag was not specified when the object was created), and the reference count reaches zero, the object manager deletes the object.</p>

<p>When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.</p>

<p>An object is <i>permanent</i> if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>.) A permanent object is created with an initial reference count of one, so the object is not deleted when the driver removes its last reference to the object.</p>

<p>To prepare a permanent object to be deleted, a driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566477">ZwMakeTemporaryObject</a> routine to make the object temporary. A driver should only delete a permanent object that it created. Use the following steps to delete a permanent object:</p>

<p>Call <b>ObDereferenceObjectWithTag</b>. </p>

<p>Get the handle to the object. If necessary, call the appropriate <b>ZwOpen<i>Xxx</i></b> or <b>ZwCreate<i>Xxx</i></b> routine to get the object handle.</p>

<p>Call <b>ZwMakeTemporaryObject</b> with the handle obtained in step 2. </p>

<p>Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> with the handle obtained in step 2.</p>

<p>If the immediate deletion of an object by the current thread might cause a deadlock, do not call <b>ObDereferenceObjectWithTag</b> to dereference the object. Instead, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557732">ObDereferenceObjectDeferDeleteWithTag</a> routine to dereference the object.</p>

<p>For example, such a deadlock can occur if <b>ObDereferenceObjectWithTag</b> is used to dereference a <a href="https://msdn.microsoft.com/43bf96ed-8be8-4670-a310-99cd7c7f9073">Kernel Transaction Manager</a> (KTM) object when a higher-level driver on the driver stack is holding a lock.</p>

<p>For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> routine is similar to <b>ObDereferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObDereferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObDereferenceObject</b> has the same effect as a call to <b>ObDereferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.</p>

<p>To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <b>!obtrace</b> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549198">IoGetDeviceObjectPointer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557732">ObDereferenceObjectDeferDeleteWithTag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558683">ObReferenceObjectByHandleWithTag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566477">ZwMakeTemporaryObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObDereferenceObjectWithTag routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
