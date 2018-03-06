---
UID: NF:portcls.PcGetTimeInterval
title: PcGetTimeInterval function
author: windows-driver-content
description: The PcGetTimeInterval function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.
old-location: audio\pcgettimeinterval.htm
old-project: audio
ms.assetid: 22afd9b9-9bed-45b0-afd8-1a5a34b9e6ad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PcGetTimeInterval, PcGetTimeInterval function [Audio Devices], audio.pcgettimeinterval, audpc-routines_a68c0cf5-01b7-4e01-a719-f0bdea2d367f.xml, portcls/PcGetTimeInterval
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcGetTimeInterval
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcGetTimeInterval function
The <b>PcGetTimeInterval</b> function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.

## Syntax

````
ULONGLONG PcGetTimeInterval(
  _In_ ULONGLONG Since
);
````

## Parameters

`Since`

Specifies the time from which to measure the interval. Typically, this function is called once with a "since" of zero to get the current time, and is called subsequently with a "since" of the recorded current time to get time intervals from that time.


## Return Value

<b>PcGetTimeInterval</b> returns the current time minus <i>Since</i>.

## Remarks

The value that is specified in parameter <i>Since</i> is measured in 100-nanosecond units. If <i>Since</i> is zero, the time returned is the number of 100-nanosecond ticks since January 1, 1601. The time units are the same as those used to specify the system time in the <a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a> function.

The following macros from portcls.h are useful for converting seconds, milliseconds, and microseconds to 100-millisecond units:

GTI_SECONDS

GTI_MILLISECONDS

GTI_MICROSECONDS

This function can be used for timing purposes by first saving the current time,

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  ULONGLONG ullTime = PcGetTimeInterval(0);</pre>
</td>
</tr>
</table></span></div>
and then checking to see whether the required interval has passed

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  if (PcGetTimeInterval(ullTime) &gt;= GTI_MILLISECONDS(5))</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcGetTimeInterval function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetTimeInterval function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>