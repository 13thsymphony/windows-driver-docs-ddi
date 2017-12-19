---
UID: NF.ks.KsFilterFactoryGetNextSiblingFilterFactory
title: KsFilterFactoryGetNextSiblingFilterFactory function
author: windows-driver-content
description: The KsFilterFactoryGetNextSiblingFilterFactory function returns the next filter factory belonging to the parent device of FilterFactory.
old-location: stream\ksfilterfactorygetnextsiblingfilterfactory.htm
old-project: stream
ms.assetid: e397d36c-3f28-4a70-9b4a-f13be094d47b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsFilterFactoryGetNextSiblingFilterFactory
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
req.alt-api: KsFilterFactoryGetNextSiblingFilterFactory
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

# KsFilterFactoryGetNextSiblingFilterFactory function



## -description
The<b> KsFilterFactoryGetNextSiblingFilterFactory</b> function returns the next filter factory belonging to the parent device of <i>FilterFactory</i>.



## -syntax

````
PKSFILTERFACTORY __inline KsFilterFactoryGetNextSiblingFilterFactory(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters

### -param FilterFactory [in]

A pointer to the <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> for which to return the next filter factory of its parent device.


## -returns
<b>KsFilterFactoryGetNextSiblingFilterFactory</b> returns a pointer to a <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> structure that represents the next sibling filter factory of <i>FilterFactory</i>. If no such filter factory exists, <b>NULL</b> is returned.


## -remarks
This call is an inline function call to <a href="stream.ksgetnextsibling">KsGetNextSibling</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.


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
<a href="stream.ksfilterfactory">KSFILTERFACTORY</a>
</dt>
<dt>
<a href="stream.ksdevicegetfirstchildfilterfactory">KsDeviceGetFirstChildFilterFactory</a>
</dt>
<dt>
<a href="stream.ksgetnextsibling">KsGetNextSibling</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetNextSiblingFilterFactory function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

