---
UID: NS.KS.KSCLOCK_FUNCTIONTABLE
title: KSCLOCK_FUNCTIONTABLE
author: windows-driver-content
description: The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock.
old-location: stream\ksclock_functiontable.htm
old-project: stream
ms.assetid: ed16588e-1c63-411d-b5c8-a8151a218328
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSCLOCK_FUNCTIONTABLE, *PKSCLOCK_FUNCTIONTABLE, KSCLOCK_FUNCTIONTABLE, PKSCLOCK_FUNCTIONTABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCLOCK_FUNCTIONTABLE
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

# KSCLOCK_FUNCTIONTABLE structure



## -description
The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock.



## -syntax

````
typedef struct {
  PFNKSCLOCK_GETTIME        GetTime;
  PFNKSCLOCK_GETTIME        GetPhysicalTime;
  PFNKSCLOCK_CORRELATEDTIME GetCorrelatedTime;
  PFNKSCLOCK_CORRELATEDTIME GetCorrelatedPhysicalTime;
} KSCLOCK_FUNCTIONTABLE, *PKSCLOCK_FUNCTIONTABLE;
````


## -struct-fields

### -field GetTime

Pointer to a driver-allocated <a href="stream.kstrclockgettime">KStrClockGetTime</a> routine.


### -field GetPhysicalTime

Pointer to a driver-allocated <a href="stream.kstrclockgetphysicaltime">KStrClockGetPhysicalTime</a> routine.


### -field GetCorrelatedTime

Pointer to a driver-allocated <a href="stream.kstrclockgetcorrelatedtime">KStrClockGetCorrelatedTime</a> routine.


### -field GetCorrelatedPhysicalTime

Pointer to a driver-allocated <a href="stream.kstrclockgetcorrelatedphysicaltime">KStrClockGetCorrelatedPhysicalTime</a> routine. 


## -remarks
Supply this structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request. The property request then returns pointers to the requested routines.

The function pointers returned in this structure are valid until the clock's file object is released.


## -requirements
<table>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCLOCK_FUNCTIONTABLE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

