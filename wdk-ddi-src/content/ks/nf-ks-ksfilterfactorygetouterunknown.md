---
UID: NF:ks.KsFilterFactoryGetOuterUnknown
title: KsFilterFactoryGetOuterUnknown function
author: windows-driver-content
description: The KsFilterFactoryGetOuterUnknown function returns the outer IUnknown of the specified filter factory.
old-location: stream\ksfilterfactorygetouterunknown.htm
old-project: stream
ms.assetid: 65244091-6089-4d0c-abf4-1178cf0bf1b5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterFactoryGetOuterUnknown
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
req.alt-api: KsFilterFactoryGetOuterUnknown
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
req.typenames: 
---

# KsFilterFactoryGetOuterUnknown function



## -description
The<b> KsFilterFactoryGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of the specified filter factory.



## -syntax

````
PUNKNOWN __inline KsFilterFactoryGetOuterUnknown(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters

### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> for which to return the outer unknown interface.


## -returns
<b>KsFilterFactoryGetOuterUnknown </b>returns the outer <b>IUnknown</b> of <i>FilterFactory</i>. The minidriver can then use it to query for other interfaces.


## -remarks
This call is an inline function call to <a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>.

For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>



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
<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfilterregisteraggregatedclientunknown.md">KsFilterRegisterAggregatedClientUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetouterunknown.md">KsPinGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetOuterUnknown function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

