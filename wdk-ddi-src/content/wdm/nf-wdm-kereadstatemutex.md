---
UID: NF.wdm.KeReadStateMutex
title: KeReadStateMutex function
author: windows-driver-content
description: The KeReadStateMutex routine returns the current state, signaled or not-signaled, of the specified mutex object.
old-location: kernel\kereadstatemutex.htm
old-project: kernel
ms.assetid: b23d846a-a1d4-4b2a-ab3c-8076302ff3fc
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: KeReadStateMutex
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
req.alt-api: KeReadStateMutex
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

# KeReadStateMutex function



## -description
The <b>KeReadStateMutex</b> routine returns the current state, signaled or not-signaled, of the specified mutex object.



## -syntax

````
LONG KeReadStateMutex(
  _In_ PRKMUTEX Mutex
);
````


## -parameters

### -param Mutex [in]

Pointer to an initialized mutex object for which the caller provides the storage.


## -returns
If the return value is 1, the state of the mutex object is signaled.


## -remarks
This routine provides an efficient way to poll the signal state of a mutex. <b>KeReadStateMutex</b> reads the state of the mutex without synchronizing its access to the mutex. Do not assume that accesses of a mutex state by <b>KeReadStateMutex</b> are mutually exclusive of accesses by routines, such as <a href="kernel.kereleasemutex">KeReleaseMutex</a> and <a href="kernel.kewaitforsingleobject">KeWaitForSingleObject</a>, that do synchronize their access to the mutex state.

For more information about mutex objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>.


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
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exinitializefastmutex">ExInitializeFastMutex</a>
</dt>
<dt>
<a href="kernel.keinitializemutex">KeInitializeMutex</a>
</dt>
<dt>
<a href="kernel.kereleasemutex">KeReleaseMutex</a>
</dt>
<dt>
<a href="kernel.kewaitforsingleobject">KeWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReadStateMutex routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

