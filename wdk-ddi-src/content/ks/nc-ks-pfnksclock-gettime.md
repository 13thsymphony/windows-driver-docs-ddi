---
UID: NC.ks.PFNKSCLOCK_GETTIME
title: PFNKSCLOCK_GETTIME
author: windows-driver-content
description: KStrClockGetPhysicalTime is a system-supplied routine that retrieves the current system time minus any suspended delta.
old-location: stream\kstrclockgetphysicaltime.htm
old-project: stream
ms.assetid: 0ffa7638-a954-40ef-88c0-e5bc7b16116d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrClockGetPhysicalTime
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
req.iface: 
---

# PFNKSCLOCK_GETTIME callback



## -description
<p><i>KStrClockGetPhysicalTime</i> is a system-supplied routine that retrieves the current system time minus any suspended delta.</p>


## -prototype

````
PFNKSCLOCK_GETTIME KStrClockGetPhysicalTime;

LONGLONG FASTCALL KStrClockGetPhysicalTime(
  _In_ PFILE_OBJECT FileObject
)
{ ... }
````


## -parameters
<dl>

### -param <i>FileObject</i> [in]

<dd>
<p>A pointer to the <a href="..\wdm\ns-wdm--file-object.md">FILE_OBJECT</a> structure to which a handle was returned when the clock instance was created.</p>
</dd>
</dl>

## -returns
<p>This routine returns the requested time value as type LONGLONG. This value is specified in 100 nanosecond units.</p>

## -remarks
<p>You can obtain an entry point for this routine by supplying a driver-allocated <a href="stream.ksclock_functiontable">KSCLOCK_FUNCTIONTABLE</a> structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>
</dt>
<dt>
<a href="stream.ksclock_functiontable">KSCLOCK_FUNCTIONTABLE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrClockGetPhysicalTime routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
