---
UID: NF.wdm.ExSystemTimeToLocalTime
title: ExSystemTimeToLocalTime function
author: windows-driver-content
description: The ExSystemTimeToLocalTime routine converts a GMT system time value to the local system time for the current time zone.
old-location: kernel\exsystemtimetolocaltime.htm
old-project: kernel
ms.assetid: d77ce60e-7b23-4f60-af63-d613ceba281e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ExSystemTimeToLocalTime
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
req.alt-api: ExSystemTimeToLocalTime
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
req.product: Windows 10 or later.
---

# ExSystemTimeToLocalTime function



## -description
The <b>ExSystemTimeToLocalTime</b> routine converts a GMT system time value to the local system time for the current time zone.


## -syntax

````
VOID ExSystemTimeToLocalTime(
  _In_  PLARGE_INTEGER SystemTime,
  _Out_ PLARGE_INTEGER LocalTime
);
````


## -parameters

### -param SystemTime [in]

A pointer to a variable set to the unbiased, GMT system time.

### -param LocalTime [out]

A pointer to the returned value for the current locale.

## -returns
None

## -remarks
<b>ExSystemTimeToLocalTime</b> subtracts the time-zone bias from the GMT system time value to compute the corresponding time at the current locale.

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
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExSystemTimeToLocalTime routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
