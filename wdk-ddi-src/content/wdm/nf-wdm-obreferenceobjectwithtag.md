---
UID: NF.wdm.ObReferenceObjectWithTag
title: ObReferenceObjectWithTag macro
author: windows-driver-content
description: The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectwithtag.htm
old-project: kernel
ms.assetid: d2b95301-c018-4a2f-801d-a78b00c8d9ca
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ObReferenceObjectWithTag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.product: Windows 10 or later.
---

# ObReferenceObjectWithTag macro



## -description
The <b>ObReferenceObjectWithTag</b> routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.



## -syntax

````
VOID ObReferenceObjectWithTag(
  _In_ PVOID Object,
  _In_ ULONG Tag
);
````


## -parameters

### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="kernel.obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.


### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.


## -remarks
<b>ObReferenceObjectWithTag</b> simply increments the pointer reference count for an object, without making any access checks on the specified object. In contrast, the <a href="kernel.obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> and <a href="kernel.obreferenceobjectbypointerwithtag">ObReferenceObjectByPointerWithTag</a> routines verify that the caller has the required access rights to the object and fail if the caller does not have these rights.

A <b>ObReferenceObjectWithTag</b> call prevents deletion of the specified object at least until the driver either calls the <a href="kernel.obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a> routine, or closes the object. After the object is no longer needed, the driver must call <b>ObDereferenceObjectWithTag</b> to remove its reference to the object.

When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.

For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.

The <a href="kernel.obreferenceobject">ObReferenceObject</a> routine is similar to <b>ObReferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObReferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObReferenceObject</b> has the same effect as a call to <b>ObReferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>
</dt>
<dt>
<a href="kernel.obreferenceobject">ObReferenceObject</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a>
</dt>
<dt>
<a href="kernel.obreferenceobjectbypointerwithtag">ObReferenceObjectByPointerWithTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectWithTag routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

