---
UID: NF.ks.KsGateRemoveOffInputFromOr
title: KsGateRemoveOffInputFromOr
author: windows-driver-content
description: The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate.
old-location: stream\ksgateremoveoffinputfromor.htm
old-project: stream
ms.assetid: 191874ec-5d08-430e-ad14-520392e1a904
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsGateRemoveOffInputFromOr
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
req.alt-api: KsGateRemoveOffInputFromOr
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
req.irql: Any level
req.iface: 
---

# KsGateRemoveOffInputFromOr function



## -description
<p>The<b> KsGateRemoveOffInputFromOr</b> function removes an existing input that is in the OFF state from an OR gate.</p>


## -syntax

````
void __inline KsGateRemoveOffInputFromOr(
  _In_ PKSGATE OrGate
);
````


## -parameters
<dl>

### -param OrGate [in]

<dd>
<p>A pointer to the <a href="..\ks\ns-ks--ksgate.md">KSGATE</a> structure representing the OR gate from which to remove an OFF input.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>KsGateRemoveOffInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.</p>

<p>This call is an empty function. It should be used for code readability and clarity. </p>

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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksgateaddoffinputtoor.md">KsGateAddOffInputToOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateaddoninputtoor.md">KsGateAddOnInputToOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateremoveoninputfromor.md">KsGateRemoveOnInputFromOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputon.md">KsGateTurnInputOn</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateturninputoff.md">KsGateTurnInputOff</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateRemoveOffInputFromOr function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
