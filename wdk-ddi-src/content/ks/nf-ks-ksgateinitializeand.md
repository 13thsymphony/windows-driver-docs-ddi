---
UID: NF.ks.KsGateInitializeAnd
title: KsGateInitializeAnd
author: windows-driver-content
description: The KsGateInitializeAnd function initializes a KSGATE structure as an AND gate and attaches it to the OR gate specified by NextOrGate.
old-location: stream\ksgateinitializeand.htm
old-project: stream
ms.assetid: ac03889a-1e02-4852-8ed9-487674c6e0de
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsGateInitializeAnd
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
req.alt-api: KsGateInitializeAnd
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

# KsGateInitializeAnd function



## -description
<p>The<b> KsGateInitializeAnd</b> function initializes a <a href="..\ks\ns-ks--ksgate.md">KSGATE</a> structure as an AND gate and attaches it to the OR gate specified by <i>NextOrGate</i>.</p>


## -syntax

````
void __inline KsGateInitializeAnd(
  _In_     PKSGATE AndGate,
  _In_opt_ PKSGATE NextOrGate
);
````


## -parameters
<dl>

### -param AndGate [in]

<dd>
<p>A pointer to the KSGATE structure to initialize as a new AND gate.</p>
</dd>

### -param NextOrGate [in, optional]

<dd>
<p>A pointer to an existing KSGATE structure to which <i>AndGate</i> attaches. This parameter should be an OR gate and is optional.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The next gate (following <i>AndGate</i>) must be an OR gate, whether it is specified in this call or later. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.</p>

<p><b>KsGateInitializeAnd</b> is an inline call to <a href="..\ks\nf-ks-ksgateinitialize.md">KsGateInitialize</a>.</p>

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
<a href="..\ks\nf-ks-ksgateinitialize.md">KsGateInitialize</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateinitializeor.md">KsGateInitializeOr</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateterminateand.md">KsGateTerminateAnd</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateterminateor.md">KsGateTerminateOr</a>
</dt>
<dt>
<a href="..\ks\ns-ks--ksgate.md">KSGATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateInitializeAnd function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
