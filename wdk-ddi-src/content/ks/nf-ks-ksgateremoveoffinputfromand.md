---
UID: NF.ks.KsGateRemoveOffInputFromAnd
title: KsGateRemoveOffInputFromAnd function
author: windows-driver-content
description: The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate.
old-location: stream\ksgateremoveoffinputfromand.htm
old-project: stream
ms.assetid: 37f463bb-6b7a-4262-9e4b-3650025acb7c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsGateRemoveOffInputFromAnd
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
req.alt-api: KsGateRemoveOffInputFromAnd
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

# KsGateRemoveOffInputFromAnd function



## -description
The<b> KsGateRemoveOffInputFromAnd</b> function removes an existing input that is in the OFF state from an AND gate.



## -syntax

````
void __inline KsGateRemoveOffInputFromAnd(
  _In_ PKSGATE AndGate
);
````


## -parameters

### -param AndGate [in]

A pointer to a <a href="stream.ksgate">KSGATE</a> structure representing the AND gate from which to remove an OFF input.


## -returns
None


## -remarks
Removing the last OFF input from the gate results in the gate opening and the transition being propagated to any gates connected to <i>AndGate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOffInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateRemoveOffInputFromAnd</b> is an inline function call to <a href="stream.ksgateturninputon">KsGateTurnInputOn</a>. If conceptually removing an existing input to the gate rather than turning it off, a minidriver should call <b>KsGateRemoveOffInputFromAnd</b> instead of <b>KsGateTurnInputOn</b>.


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
<a href="stream.ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>
</dt>
<dt>
<a href="stream.ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>
</dt>
<dt>
<a href="stream.ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>
</dt>
<dt>
<a href="stream.ksgateturninputon">KsGateTurnInputOn</a>
</dt>
<dt>
<a href="stream.ksgateturninputoff">KsGateTurnInputOff</a>
</dt>
<dt>
<a href="stream.ksgate">KSGATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateRemoveOffInputFromAnd function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

