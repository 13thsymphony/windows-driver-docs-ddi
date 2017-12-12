---
UID: NF.ks.KsGetNextSibling
title: KsGetNextSibling function
author: windows-driver-content
description: The KsGetNextSibling function returns the next sibling of a given object.
old-location: stream\ksgetnextsibling.htm
old-project: stream
ms.assetid: 509cf778-2b0c-4dd2-982d-0c7be95ad407
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsGetNextSibling
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGetNextSibling
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsGetNextSibling function



## -description
The<b> KsGetNextSibling </b>function returns the next sibling of a given object.



## -syntax

````
PVOID KsGetNextSibling(
  _In_ PVOID Object
);
````


## -parameters

### -param Object [in]

The object for which to find the next sibling.


## -returns
<b>KsGetNextSibling</b> returns the next sibling object of <i>Object</i>. If no such sibling object exists, it returns <b>NULL</b>.


## -remarks
If <i>Object</i> is a filter factory, <b>KsGetNextSibling </b>returns the next filter factory belonging to the parent device, and so on. Callers must perform appropriate typecasting to and from PVOID.

The object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Minidrivers rarely call <b>KsGetNextSibling</b> directly. There are a number of functions that are inline calls to <b>KsGetNextSibling</b> and that perform the typecasting for you: <a href="stream.ksfilterfactorygetnextsiblingfilterfactory">KsFilterFactoryGetNextSiblingFilterFactory</a>, <a href="stream.ksfiltergetnextsiblingfilter">KsFilterGetNextSiblingFilter</a>, and <a href="stream.kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
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
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
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
<a href="stream.ksfilter">KSFILTER</a>
</dt>
<dt>
<a href="stream.kspin">KSPIN</a>
</dt>
<dt>
<a href="stream.ksfilterfactorygetnextsiblingfilterfactory">KsFilterFactoryGetNextSiblingFilterFactory</a>
</dt>
<dt>
<a href="stream.ksfiltergetnextsiblingfilter">KsFilterGetNextSiblingFilter</a>
</dt>
<dt>
<a href="stream.kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetNextSibling function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

