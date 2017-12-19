---
UID: NF.ks.KsGateAddOffInputToAnd
title: KsGateAddOffInputToAnd function
author: windows-driver-content
description: The KsGateAddOffInputToAnd function adds a new input in the OFF state to a given AND gate.
old-location: stream\ksgateaddoffinputtoand.htm
old-project: stream
ms.assetid: 53e03b1d-0995-43cf-945a-22834a9e8240
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsGateAddOffInputToAnd
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
req.alt-api: KsGateAddOffInputToAnd
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

# KsGateAddOffInputToAnd function



## -description
The<b> KsGateAddOffInputToAnd</b> function adds a new input in the OFF state to a given AND gate. 



## -syntax

````
void __inline KsGateAddOffInputToAnd(
  _In_ PKSGATE AndGate
);
````


## -parameters

### -param AndGate [in]

A pointer to a <a href="stream.ksgate">KSGATE</a> structure representing the AND gate to which to add a new OFF input.


## -returns
None


## -remarks
Adding an OFF input to an open AND gate closes the gate and propagates the close down to any attached gates.

This function should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateAddOffInputToAnd</b> is an inline function call to <a href="stream.ksgateturninputoff">KsGateTurnInputOff</a>. If conceptually adding a new input to a gate, the minidriver should call <b>KsGateAddOffInputToAnd</b> rather than <b>KsGateTurnInputOff</b>. 


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
<a href="stream.ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateAddOffInputToAnd function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

