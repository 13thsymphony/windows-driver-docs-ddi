---
UID: NF.wdm.RtlTimeToTimeFields
title: RtlTimeToTimeFields function
author: windows-driver-content
description: The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure.
old-location: kernel\rtltimetotimefields.htm
old-project: kernel
ms.assetid: 128fe592-8dc1-46cf-8aa6-0f3de0896cc5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlTimeToTimeFields
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
req.alt-api: RtlTimeToTimeFields
req.alt-loc: NtosKrnl.exe,Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any level (See Remarks section)
req.product: Windows 10 or later.
---

# RtlTimeToTimeFields function



## -description
The RtlTimeToTimeFields routine converts system time into a <b>TIME_FIELDS</b> structure.


## -syntax

````
VOID RtlTimeToTimeFields(
  _In_  PLARGE_INTEGER Time,
  _Out_ PTIME_FIELDS   TimeFields
);
````


## -parameters

### -param Time [in]

Pointer to a buffer containing the absolute system time as a large integer, accurate to 100-nanosecond resolution.

### -param TimeFields [out]

Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<b>TIME_FIELDS</b>), to contain the returned information. 

## -returns
None

## -remarks
Callers of <b>RtlTimeToTimeFields</b> can be running at any IRQL if both input buffers are resident.

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
<dt>NtosKrnl.exe (kernel mode); </dt>
<dt>Ntdll.dll (user mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level (See Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>
</dt>
<dt>
<a href="kernel.exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>
</dt>
<dt>
<a href="kernel.kequerysystemtime">KeQuerySystemTime</a>
</dt>
<dt>
<a href="kernel.rtltimefieldstotime">RtlTimeFieldsToTime</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlTimeToTimeFields routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
