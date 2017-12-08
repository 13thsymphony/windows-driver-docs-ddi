---
UID: NF.wdm.ObReferenceObjectWithTag
title: ObReferenceObjectWithTag
author: windows-driver-content
description: The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectwithtag.htm
old-project: kernel
ms.assetid: d2b95301-c018-4a2f-801d-a78b00c8d9ca
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ObReferenceObjectWithTag
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
req.alt-api: ObReferenceObjectWithTag
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

# ObReferenceObjectWithTag function



## -description
<p>The <b>ObReferenceObjectWithTag</b> routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.</p>


## -syntax

````
VOID ObReferenceObjectWithTag(
  _In_ PVOID Object,
  _In_ ULONG Tag
);
````


## -parameters
<dl>

### -param Object [in]

<dd>
<p>A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="..\wdm\nf-wdm-obreferenceobjectbyhandlewithtag.md">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.</p>
</dd>

### -param Tag [in]

<dd>
<p>Specifies a four-byte, custom tag value. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -returns
<p><b>ObReferenceObjectWithTag</b> returns a value that is reserved for system use. Drivers must treat this value as VOID.</p>

## -remarks
<p><b>ObReferenceObjectWithTag</b> simply increments the pointer reference count for an object, without making any access checks on the specified object. In contrast, the <a href="..\wdm\nf-wdm-obreferenceobjectbyhandlewithtag.md">ObReferenceObjectByHandleWithTag</a> and <a href="..\wdm\nf-wdm-obreferenceobjectbypointerwithtag.md">ObReferenceObjectByPointerWithTag</a> routines verify that the caller has the required access rights to the object and fail if the caller does not have these rights.</p>

<p>A <b>ObReferenceObjectWithTag</b> call prevents deletion of the specified object at least until the driver either calls the <a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a> routine, or closes the object. After the object is no longer needed, the driver must call <b>ObDereferenceObjectWithTag</b> to remove its reference to the object.</p>

<p>When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.</p>

<p>For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.</p>

<p>The <a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a> routine is similar to <b>ObReferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObReferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObReferenceObject</b> has the same effect as a call to <b>ObReferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.</p>

<p>To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>.</p>

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
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandlewithtag.md">ObReferenceObjectByHandleWithTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbypointerwithtag.md">ObReferenceObjectByPointerWithTag</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectWithTag routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
