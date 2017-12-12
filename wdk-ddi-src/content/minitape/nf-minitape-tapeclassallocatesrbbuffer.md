---
UID: NF.minitape.TapeClassAllocateSrbBuffer
title: TapeClassAllocateSrbBuffer function
author: windows-driver-content
description: The TapeClassAllocateSrbBuffer routine allocates an Srb-&gt;DataBuffer.
old-location: storage\tapeclassallocatesrbbuffer.htm
old-project: storage
ms.assetid: f6762d9b-5a3d-49a3-b954-48e4e4a9eacb
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: TapeClassAllocateSrbBuffer
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
req.alt-api: TapeClassAllocateSrbBuffer
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
---

# TapeClassAllocateSrbBuffer function



## -description
The <b>TapeClassAllocateSrbBuffer</b> routine allocates an <b>Srb-&gt;DataBuffer</b>.



## -syntax

````
BOOLEAN TapeClassAllocateSrbBuffer(
  _Inout_ PSCSI_REQUEST_BLOCK Srb,
  _In_    ULONG               SrbBufferSize
);
````


## -parameters

### -param Srb [in, out]

Pointer to the SRB.


### -param SrbBufferSize [in]

Specifies the size, in bytes, of the <b>DataBuffer</b> to be allocated.


## -returns
<b>TapeClassAllocateSrbBuffer </b>returns <b>TRUE</b> if the <b>DataBuffer</b> was allocated successfully, and <b>FALSE</b> if the buffer was not allocated.


## -remarks
<b>TapeClassAllocateSrbBuffer </b>allocates an <b>Srb-&gt;DataBuffer</b> from nonpaged memory and initializes the members to zero. If the buffer already exists from an earlier call, it is freed and a new buffer allocated. A tape miniclass driver calls this routine to allocate a <b>DataBuffer</b> in a portable way.


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