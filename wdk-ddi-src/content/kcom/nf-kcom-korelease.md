---
UID: NF.kcom.KoRelease
title: KoRelease function
author: windows-driver-content
description: The KoRelease function decrements the reference count for the calling interface on an object.
old-location: stream\korelease.htm
old-project: stream
ms.assetid: 59be582c-0f56-45d8-b407-e588ee0f7f8b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KoRelease
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: kcom.h
req.include-header: Kcom.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KoRelease
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
req.irql: 
---

# KoRelease function



## -description
<i>This function is intended for internal use only.</i>

The <b>KoRelease</b> function decrements the reference count for the calling interface on an object. 



## -syntax

````
void KoRelease(
  _In_ REFCLSID ClassId
);
````


## -parameters

### -param ClassId [in]

The CLSID of the object whose reference count will be decremented.


## -returns
None


## -remarks


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
Header

</th>
<td width="70%">
<dl>
<dt>Kcom.h (include Kcom.h)</dt>
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
</table>