---
UID: NF:ks.KsFilterGetAndGate
title: KsFilterGetAndGate function
author: windows-driver-content
description: The KsFilterGetAndGate function returns Filter's AND gate.
old-location: stream\ksfiltergetandgate.htm
old-project: stream
ms.assetid: b5f7c4ed-0596-4e88-b987-fd454e4b4971
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterGetAndGate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFilterGetAndGate
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.typenames: 
---

# KsFilterGetAndGate function



## -description
The<b> KsFilterGetAndGate </b>function returns <i>Filter</i>'s AND gate.



## -syntax

````
PKSGATE KsFilterGetAndGate(
  _In_ PKSFILTER Filter
);
````


## -parameters

### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to acquire the corresponding AND gate.


## -returns
<b>KsFilterGetAndGate</b> returns <i>Filter</i>'s AND gate as a pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure.


## -remarks
A minidriver can use AND gates on a filter as a processing control mechanism for that filter.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgatecapturethreshold.md">KsGateCaptureThreshold</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspinattachandgate.md">KsPinAttachAndGate</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetandgate.md">KsPinGetAndGate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetAndGate function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

