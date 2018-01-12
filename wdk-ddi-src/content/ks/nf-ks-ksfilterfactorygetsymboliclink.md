---
UID: NF:ks.KsFilterFactoryGetSymbolicLink
title: KsFilterFactoryGetSymbolicLink function
author: windows-driver-content
description: The KsFilterFactoryGetSymbolicLink function returns the symbolic link associated with a given filter factory.
old-location: stream\ksfilterfactorygetsymboliclink.htm
old-project: stream
ms.assetid: db657820-75b7-49fe-904d-05f8bc45b8c5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterFactoryGetSymbolicLink
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
req.alt-api: KsFilterFactoryGetSymbolicLink
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
req.typenames: 
---

# KsFilterFactoryGetSymbolicLink function



## -description
The<b> KsFilterFactoryGetSymbolicLink</b> function returns the symbolic link associated with a given filter factory.



## -syntax

````
PUNICODE_STRING KsFilterFactoryGetSymbolicLink(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters

### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to acquire the symbolic link.


## -returns
<b>KsFilterFactoryGetSymbolicLink</b> returns a pointer to a Unicode string containing the <a href="wdkgloss.s#wdkgloss.symbolic_link#wdkgloss.symbolic_link"><i>symbolic link</i></a> for the filter factory if the call is successful, and <b>NULL</b> if unsuccessful. <b>NULL</b> indicates that no device interfaces have been registered for <i>FilterFactory</i>.


## -remarks
If <i>FilterFactory</i> has no registered device interfaces, <b>KsFilterFactoryGetSymbolicLink</b> returns <b>NULL</b>.


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