---
UID: NF.ks.KsGateRemoveOnInputFromOr
title: KsGateRemoveOnInputFromOr function
author: windows-driver-content
description: The KsGateRemoveOnInputFromOr function removes an existing input that is in the ON state from an OR gate.
old-location: stream\ksgateremoveoninputfromor.htm
old-project: stream
ms.assetid: e7226684-afbf-46e1-aeb2-6b0c60c12680
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsGateRemoveOnInputFromOr
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
req.alt-api: KsGateRemoveOnInputFromOr
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
---

# KsGateRemoveOnInputFromOr function



## -description
The<b> KsGateRemoveOnInputFromOr </b>function removes an existing input that is in the ON state from an OR gate.



## -syntax

````
void __inline KsGateRemoveOnInputFromOr(
  _In_ PKSGATE OrGate
);
````


## -parameters

### -param OrGate [in]

A pointer to a <a href="stream.ksgate">KSGATE</a> structure representing the OR gate from which to remove an ON input.


## -returns
None


## -remarks
Removing the last ON input from a given OR gate results in the gate closing and the transition being propagated to any gates connected to <i>OrGate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOnInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

This call is an inline function call to <a href="stream.ksgateturninputoff">KsGateTurnInputOff</a>. If conceptually removing an existing input to a gate, a minidriver should call <b>KsGateRemoveOnInputFromOr</b> rather than <b>KsGateTurnInputOff</b>.


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
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksgateaddoninputtoor">KsGateAddOnInputToOr</a>
</dt>
<dt>
<a href="stream.ksgateaddoffinputtoor">KsGateAddOffInputToOr</a>
</dt>
<dt>
<a href="stream.ksgateremoveoffinputfromor">KsGateRemoveOffInputFromOr</a>
</dt>
<dt>
<a href="stream.ksgateturninputon">KsGateTurnInputOn</a>
</dt>
<dt>
<a href="stream.ksgateturninputoff">KsGateTurnInputOff</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateRemoveOnInputFromOr function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

