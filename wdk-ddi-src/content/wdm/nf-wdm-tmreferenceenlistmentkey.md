---
UID: NF:wdm.TmReferenceEnlistmentKey
title: TmReferenceEnlistmentKey function
author: windows-driver-content
description: The TmReferenceEnlistmentKey routine increments the reference count for the key of a specified enlistment object and retrieves the key.
old-location: kernel\tmreferenceenlistmentkey.htm
old-project: kernel
ms.assetid: c4fd9a56-8743-4099-b261-43c1afc2a5f1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmReferenceEnlistmentKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TmReferenceEnlistmentKey
req.alt-loc: NtosKrnl.exe,Ext-MS-Win-ntos-tm-l1-1-0.dll,tm.sys
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmReferenceEnlistmentKey function



## -description
The <b>TmReferenceEnlistmentKey</b> routine increments the reference count for the key of a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> and retrieves the key.



## -syntax

````
NTSTATUS TmReferenceEnlistmentKey(
  _In_  PKENLISTMENT Enlistment,
  _Out_ PVOID        *Key
);
````


## -parameters

### -param Enlistment [in]

A pointer to an enlistment object. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.


### -param Key [out]

A pointer to a variable that receives the enlistment object's enlistment key. The caller assigns an enlistment key when it calls <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>.


## -returns
<b>TmReferenceEnlistmentKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Key</i> parameter's value is <b>NULL</b>.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The reference count of the specified enlistment object has been decremented to zero, so the reference count cannot be incremented.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The reference count is at its maximum value (0xFFFFFFFF) and cannot be incremented.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The <b>TmReferenceEnlistmentKey</b> routine increments the reference count for an enlistment object's key value, and the <a href="..\wdm\nf-wdm-tmdereferenceenlistmentkey.md">TmDereferenceEnlistmentKey</a> routine decrements the count. 

If a resource manager has defined a key value for an enlistment, the resource manager receives the key value when it calls <a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a> or when KTM calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine.

While a resource manager is processing a notification, it might use the key as a pointer to a temporary memory allocation, and it might use the reference count to determine when it should deallocate the memory.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.


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
Available in Windows Vista and later operating system versions.

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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-tmdereferenceenlistmentkey.md">TmDereferenceEnlistmentKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmReferenceEnlistmentKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

