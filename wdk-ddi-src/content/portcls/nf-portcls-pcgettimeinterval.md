---
UID: NF:portcls.PcGetTimeInterval
title: PcGetTimeInterval function
author: windows-driver-content
description: The PcGetTimeInterval function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.
old-location: audio\pcgettimeinterval.htm
old-project: audio
ms.assetid: 22afd9b9-9bed-45b0-afd8-1a5a34b9e6ad
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcGetTimeInterval
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetTimeInterval function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcGetTimeInterval
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: Any level
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# PcGetTimeInterval function



## -description
The <b>PcGetTimeInterval</b> function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.



## -syntax

````
ULONGLONG PcGetTimeInterval(
  _In_ ULONGLONG Since
);
````


## -parameters

### -param Since [in]

Specifies the time from which to measure the interval. Typically, this function is called once with a "since" of zero to get the current time, and is called subsequently with a "since" of the recorded current time to get time intervals from that time.


## -returns
<b>PcGetTimeInterval</b> returns the current time minus <i>Since</i>.


## -remarks
The value that is specified in parameter <i>Since</i> is measured in 100-nanosecond units. If <i>Since</i> is zero, the time returned is the number of 100-nanosecond ticks since January 1, 1601. The time units are the same as those used to specify the system time in the <a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a> function.

The following macros from portcls.h are useful for converting seconds, milliseconds, and microseconds to 100-millisecond units:

GTI_SECONDS

GTI_MILLISECONDS

GTI_MICROSECONDS

This function can be used for timing purposes by first saving the current time,

and then checking to see whether the required interval has passed


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
The PortCls system driver implements the PcGetTimeInterval function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
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
<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetTimeInterval function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

