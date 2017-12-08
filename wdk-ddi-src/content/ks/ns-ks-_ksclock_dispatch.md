---
UID: NS.KS._KSCLOCK_DISPATCH
title: _KSCLOCK_DISPATCH
author: windows-driver-content
description: The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object.
old-location: stream\ksclock_dispatch.htm
old-project: stream
ms.assetid: cc9b7049-7b43-4c66-9d08-93af22d92540
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSCLOCK_DISPATCH, KSCLOCK_DISPATCH, *PKSCLOCK_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCLOCK_DISPATCH
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _KSCLOCK_DISPATCH structure



## -description
The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object.


## -syntax

````
typedef struct _KSCLOCK_DISPATCH {
  PFNKSPINSETTIMER       SetTimer;
  PFNKSPINCANCELTIMER    CancelTimer;
  PFNKSPINCORRELATEDTIME CorrelatedTime;
  PFNKSPINRESOLUTION     Resolution;
} KSCLOCK_DISPATCH, *PKSCLOCK_DISPATCH;
````


## -struct-fields

### -field SetTimer

Optionally contains a pointer to an alternate function to use in generating DPC timer callbacks based on a presentation time. If this is set, this function is used to set timers based on deltas to the current presentation time in order to generate event notifications. If an alternate function is specified to set timers, a corresponding <b>CancelTimer</b> function must also be provided. This is set to <b>NULL</b> if the default <a href="kernel.kesettimerex">KeSetTimerEx</a> function is used to approximate the next notification time. This would normally be set only if a <b>KeSetTimerEx</b> function was being used. The function must have the same characteristics as the default function.
The function should be prototyped as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  BOOLEAN SetTimer (IN PKSPIN Pin,
    IN PKTIMER Timer,
    IN LARGE_INTEGER DueTime,
    IN PKDPC Dpc);</pre>
</td>
</tr>
</table></span></div>
See the documentation for <b>KeSetTimerEx</b> for details on implementation of this function. Any client implementation must behave in a similar manner.

### -field CancelTimer

Optionally contains an alternate function to use in canceling outstanding timer callbacks. If an alternate function is provided to cancel timers, a corresponding <i>SetTimer</i> function must also be provided. This is set to <b>NULL</b> if the default <b>KeCancelTimer</b> function is to be used. The function must have the same characteristics as the default function.
The function should be prototyped as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  BOOLEAN CancelTimer (IN PKSPIN Pin,
    IN PKTIMER Timer);</pre>
</td>
</tr>
</table></span></div>
See the documentation for <b>KeCancelTimer</b> for details on the implementation of this function. Any client implementation must behave in a similar manner.

### -field CorrelatedTime

A pointer to a function to retrieve the current clock time and a correlated system time as an atomic operation. The function should be prototyped as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  LONGLONG CorrelatedTime (IN PKSPIN Pin,
    OUT PLONGLONG SystemTime);</pre>
</td>
</tr>
</table></span></div>
The current clock time should be returned and the current system time should be placed in <b>SystemTime</b>.

### -field Resolution

A pointer to a function to specify the resolution of the clock. This corresponds to the KS property <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>. This function should report the granularity in terms of 100-nanosecond units. For more information, see the KS documentation on KSPROPERTY_CLOCK_RESOLUTION. 
The function should be prototyped as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    void Resolution (IN PKSPIN Pin,
        OUT PKSRESOLUTION Resolution);</pre>
</td>
</tr>
</table></span></div>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
<dt>
<a href="stream.kspin">KSPIN</a>
</dt>
<dt>
<a href="stream.ksresolution">KSRESOLUTION</a>
</dt>
<dt>
<a href="kernel.kesettimerex">KeSetTimerEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCLOCK_DISPATCH structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
