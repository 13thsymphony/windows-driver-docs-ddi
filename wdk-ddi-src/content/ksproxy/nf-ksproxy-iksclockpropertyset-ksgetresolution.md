---
UID: NF.ksproxy.IKsClockPropertySet.KsGetResolution
title: IKsClockPropertySet::KsGetResolution
author: windows-driver-content
description: The KsGetResolution method retrieves the clock resolution from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetresolution.htm
ms.assetid: 507d41ae-31b9-4807-99af-9ec48eb2b5aa
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsClockPropertySet.KsGetResolution
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
ms.keywords: IKsClockPropertySet, KsGetResolution, IKsClockPropertySet::KsGetResolution
req.iface: IKsClockPropertySet
---

# IKsClockPropertySet::KsGetResolution method



## -description
<p>The <b>KsGetResolution</b> method retrieves the clock resolution from the underlying clock.</p>


## -syntax

````
HRESULT KsGetResolution(
  [out] KSRESOLUTION *Resolution
);
````


## -parameters
<dl>

### -param <i>Resolution</i> [out]

<dd>
<p>Pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566806">KSRESOLUTION</a> structure that contains the granularity and error of the underlying clock.</p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns an error code.</p>

## -remarks
<p>The <b>KsGetResolution</b> method retrieves the underlying clock's resolution property, which specifies the underlying clock's increment granularity and notification error in terms of 100-nanosecond units. The best granularity would be one 100-nanosecond unit; less granular increments would contain larger numbers. The least amount of notification error above and beyond the clock granularity would be reported as zero 100-nanosecond units, and less accurate clocks would use larger numbers to indicate +/− error. The proxy can use this resolution property to determine maximum error and resolution in event notification and synchronization.</p>

<p>The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property to retrieve the clock resolution. </p>

<p>The <b>KsGetResolution</b> method retrieves the underlying clock's resolution property, which specifies the underlying clock's increment granularity and notification error in terms of 100-nanosecond units. The best granularity would be one 100-nanosecond unit; less granular increments would contain larger numbers. The least amount of notification error above and beyond the clock granularity would be reported as zero 100-nanosecond units, and less accurate clocks would use larger numbers to indicate +/− error. The proxy can use this resolution property to determine maximum error and resolution in event notification and synchronization.</p>

<p>The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property to retrieve the clock resolution. </p>

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
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566806">KSRESOLUTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsGetResolution method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
