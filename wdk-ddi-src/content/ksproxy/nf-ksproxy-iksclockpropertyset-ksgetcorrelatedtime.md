---
UID: NF.ksproxy.IKsClockPropertySet.KsGetCorrelatedTime
title: IKsClockPropertySet::KsGetCorrelatedTime method
author: windows-driver-content
description: The KsGetCorrelatedTime method retrieves the current time and the correlated system time from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetcorrelatedtime.htm
old-project: stream
ms.assetid: b91f33b3-2706-4c94-9960-ceea023891af
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsClockPropertySet, IKsClockPropertySet::KsGetCorrelatedTime, KsGetCorrelatedTime
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
req.alt-api: IKsClockPropertySet.KsGetCorrelatedTime
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

# IKsClockPropertySet::KsGetCorrelatedTime method



## -description
The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system time from the underlying clock. 



## -syntax

````
HRESULT KsGetCorrelatedTime(
  [out] KSCORRELATED_TIME *CorrelatedTime
);
````


## -parameters

### -param CorrelatedTime [out]

Pointer to a variable that receives a <a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a> structure that contains the current clock time along with the correlated system time.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system in an atomic operation. 

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to retrieve the correlated time. 


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
<a href="stream.iksclockpropertyset_kssetcorrelatedtime">IKsClockPropertySet::KsSetCorrelatedTime</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsGetCorrelatedTime method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

