---
UID: NF.wdm.KeTryToAcquireGuardedMutex
title: KeTryToAcquireGuardedMutex function
author: windows-driver-content
description: The KeTryToAcquireGuardedMutex routine acquires a guarded mutex, if available.
old-location: kernel\ketrytoacquireguardedmutex.htm
old-project: kernel
ms.assetid: 5fa704ec-5068-42e9-8d52-2f775fd0e5c9
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: KeTryToAcquireGuardedMutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeTryToAcquireGuardedMutex
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlKeApcLte1, HwStorPortProhibitedDDIs
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

# KeTryToAcquireGuardedMutex function



## -description
The <b>KeTryToAcquireGuardedMutex</b> routine acquires a guarded mutex, if available.



## -syntax

````
BOOLEAN KeTryToAcquireGuardedMutex(
  _Inout_ PKGUARDED_MUTEX Mutex
);
````


## -parameters

### -param Mutex [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554235">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -returns
<b>KeTryToAcquireGuardedMutex</b> returns <b>TRUE</b> if the mutex is acquired, and <b>FALSE</b> otherwise.


## -remarks
Use <b>KeReleaseGuardedMutex</b> to release the mutex.

<b>KeTryToAcquireGuardedMutex</b> returns immediately, regardless of whether it can acquire the mutex. Use <b>KeAcquireGuardedMutex</b> to put the calling thread into a wait state until mutex becomes available.

A thread that calls <b>KeTryToAcquireGuardedMutex</b> implicitly enters a guarded region, where all APCs are disabled. They remain disabled until the thread releases the mutex with <b>KeReleaseGuardedMutex</b>.

For more information about guarded mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545716">Fast Mutexes and Guarded Mutexes</a>.


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
Available in Windows Server 2003 and later versions of Windows.

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
<a href="devtest.wdm_irqlkeapclte1">IrqlKeApcLte1</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.kereleaseguardedmutex">KeReleaseGuardedMutex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeTryToAcquireGuardedMutex routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

