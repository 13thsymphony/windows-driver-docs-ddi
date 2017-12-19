---
UID: NF.ksproxy.IKsClockPropertySet.KsGetPhysicalTime
title: IKsClockPropertySet::KsGetPhysicalTime method
author: windows-driver-content
description: The KsGetPhysicalTime method retrieves the physical time from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetphysicaltime.htm
old-project: stream
ms.assetid: 25875f28-292f-40d9-8b29-ec9af49b0bc0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsClockPropertySet, IKsClockPropertySet::KsGetPhysicalTime, KsGetPhysicalTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsClockPropertySet.KsGetPhysicalTime
req.alt-loc: ksproxy.h
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

# IKsClockPropertySet::KsGetPhysicalTime method



## -description
The <b>KsGetPhysicalTime</b> method retrieves the physical time from the underlying clock. 



## -syntax

````
HRESULT KsGetPhysicalTime(
  [out] LONGLONG *Time
);
````


## -parameters

### -param Time [out]

Pointer to a variable that receives the current physical time.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
The physical time is based on some underlying physical clock that always progresses, even if the physical type of clock must be changed in real time. Other physical clocks use an underlying clock's physical time for rate matching.

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to retrieve the physical time. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.iksclockpropertyset_kssetphysicaltime">IKsClockPropertySet::KsSetPhysicalTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsGetPhysicalTime method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

