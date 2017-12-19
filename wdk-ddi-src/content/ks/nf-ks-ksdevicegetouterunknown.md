---
UID: NF.ks.KsDeviceGetOuterUnknown
title: KsDeviceGetOuterUnknown function
author: windows-driver-content
description: The KsDeviceGetOuterUnknown function returns the outer IUnknown of the AVStream device specified by Device.
old-location: stream\ksdevicegetouterunknown.htm
old-project: stream
ms.assetid: a63cdc50-6bbb-4bff-8536-0bf31fed01de
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsDeviceGetOuterUnknown
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
req.alt-api: KsDeviceGetOuterUnknown
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
---

# KsDeviceGetOuterUnknown function



## -description
The<b> KsDeviceGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the AVStream device specified by <i>Device</i>.



## -syntax

````
PUNKNOWN __inline KsDeviceGetOuterUnknown(
  _In_ PKSDEVICE Device
);
````


## -parameters

### -param Device [in]

A pointer to a <a href="stream.ksdevice">KSDEVICE</a> structure for which to get the outer unknown interface.


## -returns
Returns a pointer to an outer <b>IUnknown</b> of <i>Device</i>. This interface can then be used to query for other interfaces.


## -remarks
This call is an inline function call to <a href="stream.ksgetouterunknown">KsGetOuterUnknown</a>.


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksgetouterunknown">KsGetOuterUnknown</a>
</dt>
<dt>
<a href="stream.ksfilterfactorygetouterunknown">KsFilterFactoryGetOuterUnknown</a>
</dt>
<dt>
<a href="stream.ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>
</dt>
<dt>
<a href="stream.kspingetouterunknown">KsPinGetOuterUnknown</a>
</dt>
<dt>
<a href="stream.ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
</dt>
<dt>
<a href="..\ks\nn-ks-ikscontrol~r1.md">IKsControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceGetOuterUnknown function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

