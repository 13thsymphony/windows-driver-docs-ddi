---
UID: NF.wdm.ObDereferenceObjectDeferDeleteWithTag
title: ObDereferenceObjectDeferDeleteWithTag function
author: windows-driver-content
description: The ObDereferenceObjectDeferDeleteWithTag routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obdereferenceobjectdeferdeletewithtag.htm
old-project: kernel
ms.assetid: 72f1622f-a364-4d93-9c49-c4c7bcda6488
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ObDereferenceObjectDeferDeleteWithTag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObDereferenceObjectDeferDeleteWithTag
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
req.product: Windows 10 or later.
---

# ObDereferenceObjectDeferDeleteWithTag function



## -description
The <b>ObDereferenceObjectDeferDeleteWithTag</b> routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>. 



## -syntax

````
VOID ObDereferenceObjectDeferDeleteWithTag(
  _In_ PVOID Object,
  _In_ ULONG Tag
);
````


## -parameters

### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="kernel.obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> routine after it opens the object. 


### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section. 


## -returns
None


## -remarks
<b>ObDereferenceObjectDeferDeleteWithTag</b> is similar to <a href="kernel.obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a> except that, when the reference count of the object reaches zero, <b>ObDereferenceObjectDeferDeleteWithTag</b> passes the object deletion request to a worker thread. The worker thread, which runs at IRQL = PASSIVE_LEVEL, later deletes the object.

If the immediate deletion of an object by the current thread might cause a deadlock, do not call <b>ObDereferenceObjectWithTag</b> to dereference the object. Instead, call <b>ObDereferenceObjectDeferDeleteWithTag</b> to dereference the object.

For example, such a deadlock can occur if <b>ObDereferenceObjectWithTag</b> is used to dereference a <a href="https://msdn.microsoft.com/43bf96ed-8be8-4670-a310-99cd7c7f9073">Kernel Transaction Manager</a> (KTM) object when a higher-level driver on the driver stack is holding a lock.

For more information about object permanence and object attributes, see <a href="kernel.obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>. For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.

The <a href="kernel.obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a> routine is similar to <b>ObDereferenceObjectDeferDeleteWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObDereferenceObjectDeferDelete</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObDereferenceObjectDeferDelete</b> has the same effect as a call to <b>ObDereferenceObjectDeferDeleteWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>. 


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
Available in Windows 7 and later versions of the Windows operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
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
<a href="kernel.obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a>
</dt>
<dt>
<a href="kernel.obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObDereferenceObjectDeferDeleteWithTag routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

