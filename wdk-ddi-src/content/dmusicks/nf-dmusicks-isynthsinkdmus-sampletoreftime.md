---
UID: NF.dmusicks.ISynthSinkDMus.SampleToRefTime
title: ISynthSinkDMus::SampleToRefTime
author: windows-driver-content
description: The SampleToRefTime method converts a sample time to a reference time.
old-location: audio\isynthsinkdmus_sampletoreftime.htm
old-project: audio
ms.assetid: b2d54ee9-78aa-4799-a06d-6c79000d3e32
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ISynthSinkDMus, SampleToRefTime, ISynthSinkDMus::SampleToRefTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISynthSinkDMus.SampleToRefTime
req.alt-loc: dmusicks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: ISynthSinkDMus
---

# ISynthSinkDMus::SampleToRefTime method



## -description
<p>The <code>SampleToRefTime</code> method converts a sample time to a reference time.</p>


## -syntax

````
NTSTATUS SampleToRefTime(
  [in]  LONGLONG       llSampleTime,
  [out] REFERENCE_TIME *prtTime
);
````


## -parameters
<dl>

### -param llSampleTime [in]

<dd>
<p>Specifies the sample time being passed in.</p>
</dd>

### -param prtTime [out]

<dd>
<p>Output pointer for the reference time. This parameter is a pointer to a caller-allocated variable into which the method writes the calculated reference time. Reference time is measured in 100-nanosecond units.</p>
</dd>
</dl>

## -returns
<p><code>SampleToRefTime</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.</p>

## -remarks
<p>The <code>SampleToRefTime</code> method accepts a sample time as an input parameter, converts the sample time to a reference time, and outputs the reference time to a location specified by the caller.</p>

<p>The calculation of reference time from sample time to reference time depends on the sampling frequency. For example, if the output buffer is in a 44.2 kHz format, a sample time of 44,200 is equivalent to a reference time of one second.</p>

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
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-isynthsinkdmus.md">ISynthSinkDMus</a>
</dt>
<dt>
<a href="audio.idirectmusicsynthsink_sampletoreftime">IDirectMusicSynthSink::SampleToRefTime</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20ISynthSinkDMus::SampleToRefTime method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
