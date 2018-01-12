---
UID: NF:ks.KsFilterGetParentFilterFactory
title: KsFilterGetParentFilterFactory function
author: windows-driver-content
description: The KsFilterGetParentFilterFactory function returns the parent filter factory of the given filter.
old-location: stream\ksfiltergetparentfilterfactory.htm
old-project: stream
ms.assetid: 08b02410-3e18-4bfd-8f10-2a12a5f94e16
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterGetParentFilterFactory
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
req.alt-api: KsFilterGetParentFilterFactory
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

# KsFilterGetParentFilterFactory function



## -description
The<b> KsFilterGetParentFilterFactory</b> function returns the parent filter factory of the given filter.



## -syntax

````
PKSFILTERFACTORY __inline KsFilterGetParentFilterFactory(
  _In_ PKSFILTER Filter
);
````


## -parameters

### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to return the parent filter factory.


## -returns
<b>KsFilterGetParentFilterFactory</b> returns a pointer to the parent <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure of <i>Filter.</i> This is the AVStream filter factory from which <i>Filter</i> was created.


## -remarks
This call is an inline function call to <a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.


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
<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetParentFilterFactory function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

