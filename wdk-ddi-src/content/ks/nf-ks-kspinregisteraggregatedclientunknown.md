---
UID: NF.ks.KsPinRegisterAggregatedClientUnknown
title: KsPinRegisterAggregatedClientUnknown function
author: windows-driver-content
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\kspinregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: 302d87be-a276-49ea-98f2-89e1f231c3c6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsPinRegisterAggregatedClientUnknown
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
req.alt-api: KsPinRegisterAggregatedClientUnknown
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
---

# KsPinRegisterAggregatedClientUnknown function



## -description
This inline function is a wrapper for <a href="stream.ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>.



## -syntax

````
PUNKNOWN __inline KsPinRegisterAggregatedClientUnknown(
  _In_ PKSPIN   Pin,
  _In_ PUNKNOWN ClientUnknown
);
````


## -parameters

### -param Pin [in]

A pointer to a <a href="stream.kspin">KSPIN</a> structure.


### -param ClientUnknown [in]

A pointer to an <b>IUnknown</b> interface.


## -returns
<b>KsPinRegisterAggregatedClientUnknown</b> returns the newly created aggregate object.


## -remarks
This inline function only performs a typecast and then calls <a href="stream.ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>.


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
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinRegisterAggregatedClientUnknown function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

