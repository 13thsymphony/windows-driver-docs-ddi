---
UID: NF.wdm.KeQueryTimeIncrement
title: KeQueryTimeIncrement
author: windows-driver-content
description: The KeQueryTimeIncrement routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.
old-location: kernel\kequerytimeincrement.htm
old-project: kernel
ms.assetid: f8291e2b-a7a1-4a19-9137-fcd93e62bbaf
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KeQueryTimeIncrement
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
req.alt-api: KeQueryTimeIncrement
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
req.irql: Any level
req.iface: 
req.product: Windows 10 or later.
---

# KeQueryTimeIncrement function



## -description
<p>The <b>KeQueryTimeIncrement</b> routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.</p>


## -syntax

````
ULONG KeQueryTimeIncrement(void);
````


## -parameters


## -returns
<p><b>KeQueryTimeIncrement</b> returns a ULONG value indicating the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.</p>

<p><b>KeQueryTimeIncrement</b> returns a ULONG value indicating the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.</p>

<p><b>KeQueryTimeIncrement</b> returns a ULONG value indicating the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.</p>

## -remarks
<p>At startup time, the operating system determines the time increment to use for the system time. This time increment remains constant until the computer restarts. During this time, calls to <b>KeQueryTimeIncrement</b> always return the same time increment value. The time increment does not change while the computer is running, and it does not change as the result of a suspend-resume cycle.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kequerytickcount.md">KeQueryTickCount</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryTimeIncrement routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
