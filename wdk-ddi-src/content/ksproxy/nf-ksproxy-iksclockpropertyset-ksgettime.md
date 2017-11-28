---
UID: NF.ksproxy.IKsClockPropertySet.KsGetTime
title: IKsClockPropertySet::KsGetTime
author: windows-driver-content
description: The KsGetTime method retrieves the time of the underlying clock.
old-location: stream\iksclockpropertyset_ksgettime.htm
old-project: stream
ms.assetid: 0d22baeb-d08f-4554-9af4-dae9480a471a
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IKsClockPropertySet, KsGetTime, IKsClockPropertySet::KsGetTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsClockPropertySet.KsGetTime
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
req.iface: IKsClockPropertySet
---

# IKsClockPropertySet::KsGetTime method



## -description
<p>The <b>KsGetTime</b> method retrieves the time of the underlying clock. </p>


## -syntax

````
HRESULT KsGetTime(
  [out] LONGLONG *Time
);
````


## -parameters
<dl>

### -param <i>Time</i> [out]

<dd>
<p>Pointer to a variable that receives the current clock time.</p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns an error code.</p>

## -remarks
<p>The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time. </p>

<p>The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559763">IKsClockPropertySet::KsSetTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsGetTime method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
