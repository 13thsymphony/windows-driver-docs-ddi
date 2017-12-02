---
UID: NF.ks.KsFilterReleaseControl
title: KsFilterReleaseControl
author: windows-driver-content
description: The KsFilterReleaseControl function releases the control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleasecontrol.htm
old-project: stream
ms.assetid: 4f868e88-ef5c-4fad-be53-2b5116a6385b
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsFilterReleaseControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFilterReleaseControl
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
req.irql: PASSIVE_LEVEL
req.iface: 
---

# KsFilterReleaseControl function



## -description
<p>The<b> KsFilterReleaseControl </b>function releases the control mutex for the AVStream filter specified by <i>Filter</i>.</p>


## -syntax

````
void __inline KsFilterReleaseControl(
  _In_ PKSFILTER Filter
);
````


## -parameters
<dl>

### -param Filter [in]

<dd>
<p>A pointer to a <a href="..\ks\ns-ks--ksfilter.md">KSFILTER</a> structure representing the AVStream filter for which to release the control mutex.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>This function is an inline call to <a href="..\ks\nf-ks-ksreleasecontrol.md">KsReleaseControl</a> with the appropriate typecasting. When manipulating a filter, minidrivers should call this function instead of calling <b>KsReleaseControl</b> directly.</p>

<p>For a description of the filter control mutex, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksfilteracquirecontrol.md">KsFilterAcquireControl</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksreleasecontrol.md">KsReleaseControl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterReleaseControl function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
