---
UID: NS.ks.PKSRATE
title: PKSRATE
author: windows-driver-content
description: The query is passed a KSRATE structure appended to the property containing the rate request (known as a KSRATE_CAPABILITY structure), and is returned a KSRATE structure filled in with the capability given the rate request.
old-location: stream\ksrate.htm
old-project: stream
ms.assetid: dc8f23d5-14bb-43be-807a-041ca9c30a76
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: PKSRATE, KSRATE, *PKSRATE
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
req.alt-api: KSRATE
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

# PKSRATE structure



## -description
<p>The query is passed a KSRATE structure appended to the property containing the rate request (known as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566754">KSRATE_CAPABILITY</a> structure), and is returned a KSRATE structure filled in with the capability given the rate request.</p>


## -syntax

````
typedef struct {
  LONGLONG        PresentationStart;
  LONGLONG        Duration;
  KSPIN_INTERFACE Interface;
  LONG            Rate;
  ULONG           Flags;
} KSRATE, *PKSRATE;
````


## -struct-fields
<dl>

### -field <b>PresentationStart</b>

<dd>
<p>Specifies the start point for the rate in presentation time units.</p>
</dd>

### -field <b>Duration</b>

<dd>
<p>Specifies the duration of the rate in presentation time units.</p>
</dd>

### -field <b>Interface</b>

<dd>
<p>A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> that specifies either the interface used in the connection this rate request is being sent to, or the interface of a related connection. This allows the time units to be interpreted by the pin.</p>
</dd>

### -field <b>Rate</b>

<dd>
<p>Specifies the rate in terms of 1/10th percentage points, where 1000 is the nominal 1.0 rate, 500 is 0.5 rate, and so on. Negative numbers indicate reverse rates.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Possible flag values are listed in the following table.</p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>KSRATE_NOPRESENTATIONSTART</p>
</td>
<td>
<p>Specifies that there is no valid start time in this rate change request or query.</p>
</td>
</tr>
<tr>
<td>
<p>KSRATE_NOPRESENTATIONDURATION</p>
</td>
<td>
<p>Specifies that there is no valid duration in this rate change request or query.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566754">KSRATE_CAPABILITY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSRATE structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
