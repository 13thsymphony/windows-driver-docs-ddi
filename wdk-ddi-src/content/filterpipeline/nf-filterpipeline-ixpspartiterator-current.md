---
UID: NF.filterpipeline.IXpsPartIterator.Current
title: IXpsPartIterator::Current method
author: windows-driver-content
description: The Current method provides the current URI and part.
old-location: print\ixpspartiterator_current.htm
old-project: print
ms.assetid: ccc8125a-c571-4267-860a-11fc313e395c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IXpsPartIterator, IXpsPartIterator::Current, Current
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IXpsPartIterator.Current
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IXpsPartIterator::Current method



## -description
The <code>Current</code> method provides the current URI and part.



## -syntax

````
HRESULT Current(
  [out] BSTR     *pUri,
  [out] IUnknown **ppXpsPart
);
````


## -parameters

### -param pUri [out]

A pointer to the URI of the part. If <b>NULL</b>, the <i>ppXpsPartparameter</i> might still be valid.


### -param ppXpsPart [out]

The current part in the iterator. If <b>NULL</b>, the <i>pUri</i> parameter might still be valid.


## -returns
<code>Current</code> returns an <b>HRESULT</b> value.


## -remarks
Filters should call the <a href="print.ixpspartiterator_isdone">IXpsPartIterator::IsDone</a> method before calling <code>Current</code>. One or both parameters can be <b>NULL</b>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IDL

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>