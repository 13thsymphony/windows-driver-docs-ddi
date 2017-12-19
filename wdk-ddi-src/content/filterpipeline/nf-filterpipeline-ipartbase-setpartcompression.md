---
UID: NF.filterpipeline.IPartBase.SetPartCompression
title: IPartBase::SetPartCompression method
author: windows-driver-content
description: The SetPartCompression method sets the compression of the part.
old-location: print\ipartbase_setpartcompression.htm
old-project: print
ms.assetid: 4e407266-4789-4de7-bcc8-7e9bb54804ed
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPartBase, IPartBase::SetPartCompression, SetPartCompression
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
req.alt-api: IPartBase.SetPartCompression
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

# IPartBase::SetPartCompression method



## -description
The <b>SetPartCompression</b> method sets the compression of the part.



## -syntax

````
HRESULT SetPartCompression(
  [in] EXpsCompressionOptions compression
);
````


## -parameters

### -param compression [in]

A <a href="print.expscompressionoptions">ExpsCompressionOptions</a>-typed value that describes the compression option for the part.


## -returns
<b>SetPartCompression</b> returns an <b>HRESULT</b> value.


## -remarks


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