---
UID: NE.ks.KSDEGRADE_STANDARD
title: KSDEGRADE_STANDARD
author: windows-driver-content
description: The KSDEGRADE_STANDARD enumeration lists different types of degradation.
old-location: stream\ksdegrade_standard.htm
old-project: stream
ms.assetid: 5790ce0e-13f8-4700-8b25-a5375dd83758
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSDEGRADE_STANDARD
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

# KSDEGRADE_STANDARD enumeration



## -description
<p>The KSDEGRADE_STANDARD enumeration lists different types of degradation.</p>


## -syntax

````
typedef enum  { 
  KSDEGRADE_STANDARD_SAMPLE       = 0,
  KSDEGRADE_STANDARD_QUALITY      = 1,
  KSDEGRADE_STANDARD_COMPUTATION  = 2,
  KSDEGRADE_STANDARD_SKIP         = 3
} KSDEGRADE_STANDARD;
````


## -enum-fields
<dl>

### -field <a id="KSDEGRADE_STANDARD_SAMPLE"></a><a id="ksdegrade_standard_sample"></a><b>KSDEGRADE_STANDARD_SAMPLE</b>

<dd>
<p>Specifies sample degradation.</p>
</dd>

### -field <a id="KSDEGRADE_STANDARD_QUALITY"></a><a id="ksdegrade_standard_quality"></a><b>KSDEGRADE_STANDARD_QUALITY</b>

<dd>
<p>Specifies quality degradation.</p>
</dd>

### -field <a id="KSDEGRADE_STANDARD_COMPUTATION"></a><a id="ksdegrade_standard_computation"></a><b>KSDEGRADE_STANDARD_COMPUTATION</b>

<dd>
<p>Specifies computation degradation.</p>
</dd>

### -field <a id="KSDEGRADE_STANDARD_SKIP"></a><a id="ksdegrade_standard_skip"></a><b>KSDEGRADE_STANDARD_SKIP</b>

<dd>
<p>Requests to skip ahead a specified delta in the data stream.</p>
</dd>
</dl>

## -remarks
<p>For more information, see <a href="NULL">Quality Management</a>.</p>

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
<a href="stream.ksdegrade">KSDEGRADE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDEGRADE_STANDARD enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
