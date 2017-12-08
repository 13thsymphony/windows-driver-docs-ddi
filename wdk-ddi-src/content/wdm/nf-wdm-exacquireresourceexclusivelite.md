---
UID: NF.wdm.ExAcquireResourceExclusiveLite
title: ExAcquireResourceExclusiveLite function
author: windows-driver-content
description: The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread.
old-location: kernel\exacquireresourceexclusivelite.htm
old-project: kernel
ms.assetid: c7f8a6c5-15d5-4a24-a351-4fa5d6c72fbd
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ExAcquireResourceExclusiveLite
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
req.alt-api: ExAcquireResourceExclusiveLite
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: ExclusiveResourceAccess, IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# ExAcquireResourceExclusiveLite function



## -description
The <b>ExAcquireResourceExclusiveLite</b> routine acquires the given resource for exclusive access by the calling thread.


## -syntax

````
BOOLEAN ExAcquireResourceExclusiveLite(
  _Inout_ PERESOURCE Resource,
  _In_    BOOLEAN    Wait
);
````


## -parameters

### -param Resource [in, out]

A pointer to the resource to acquire.

### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired. 

## -returns
<b>ExAcquireResourceExclusiveLite</b> returns <b>TRUE</b> if the resource is acquired. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and exclusive access cannot be granted immediately.

## -remarks
The following list describes whether and when a caller is given exclusive access to a given resource:

If the resource is currently not owned, exclusive access is granted immediately to the current thread.

If the caller already had acquired the resource for exclusive access, the current thread is granted the same type of access recursively.

If the caller has shared access to the resource, the caller must release the lock before it attempts to reacquire it exclusively.

If the resource is currently owned as exclusive by another thread, or if the caller only has shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

The caller can release the resource by calling either <a href="kernel.exreleaseresourcelite">ExReleaseResourceLite</a> or <a href="kernel.exreleaseresourceforthreadlite">ExReleaseResourceForThreadLite</a>.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="kernel.keentercriticalregion">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="kernel.keleavecriticalregion">KeLeaveCriticalRegion</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.

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
&lt;= APC_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_exclusiveresourceaccess">ExclusiveResourceAccess</a>, <a href="devtest.wdm_irqlexapclte3">IrqlExApcLte3</a>, <a href="devtest.wdm_withincriticalregion">WithinCriticalRegion</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_withincriticalregion">WithinCriticalRegion(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exacquireresourcesharedlite">ExAcquireResourceSharedLite</a>
</dt>
<dt>
<a href="kernel.exgetexclusivewaitercount">ExGetExclusiveWaiterCount</a>
</dt>
<dt>
<a href="kernel.exgetsharedwaitercount">ExGetSharedWaiterCount</a>
</dt>
<dt>
<a href="kernel.exinitializeresourcelite">ExInitializeResourceLite</a>
</dt>
<dt>
<a href="kernel.exreinitializeresourcelite">ExReinitializeResourceLite</a>
</dt>
<dt>
<a href="kernel.exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>
</dt>
<dt>
<a href="kernel.exreleaseresourceforthreadlite">ExReleaseResourceForThreadLite</a>
</dt>
<dt>
<a href="kernel.keentercriticalregion">KeEnterCriticalRegion</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAcquireResourceExclusiveLite routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
