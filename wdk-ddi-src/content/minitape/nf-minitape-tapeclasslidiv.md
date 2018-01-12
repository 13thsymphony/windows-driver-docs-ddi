---
UID: NF:minitape.TapeClassLiDiv
title: TapeClassLiDiv function
author: windows-driver-content
description: The TapeClassLiDiv routine performs a division of the two indicated integers.
old-location: storage\tapeclasslidiv.htm
old-project: storage
ms.assetid: 13c449c6-6e2b-434e-8948-62c8af237173
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: TapeClassLiDiv
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TapeClassLiDiv
req.alt-loc: Tape.lib,Tape.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Tape.lib
req.dll: 
req.irql: 
req.typenames: *PTAPE_STATUS, TAPE_STATUS
---

# TapeClassLiDiv function



## -description
The <b>TapeClassLiDiv</b> routine performs a division of the two indicated integers. 



## -syntax

````
LARGE_INTEGER TapeClassLiDiv(
  _In_ LARGE_INTEGER Dividend,
  _In_ LARGE_INTEGER Divisor
);
````


## -parameters

### -param Dividend [in]

Contains the dividend.


### -param Divisor [in]

Contains the divisor.


## -returns
<b>TapeClassLiDiv</b> returns the result of the division. 


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
<dt>Minitape.h (include Minitape.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Tape.lib</dt>
</dl>
</td>
</tr>
</table>