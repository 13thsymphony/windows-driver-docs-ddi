---
UID: NE.strmini.STREAM_BUFFER_TYPE
title: STREAM_BUFFER_TYPE
author: windows-driver-content
description: This enumeration defines the buffer types for StreamClassGetPhysicalAddress.
old-location: stream\stream_buffer_type.htm
old-project: stream
ms.assetid: 7C9E1D94-BF59-4302-BEE8-24546C8AE7E6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: STREAM_BUFFER_TYPE, STREAM_BUFFER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_BUFFER_TYPE
req.alt-loc: Strmini.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# STREAM_BUFFER_TYPE enumeration



## -description
This enumeration defines the buffer types for <a href="https://msdn.microsoft.com/library/windows/hardware/ff568247">StreamClassGetPhysicalAddress</a>.



## -syntax

````
typedef enum  { 
  PerRequestExtension,
  DmaBuffer,
  SRBDataBuffer
} STREAM_BUFFER_TYPE;
````


## -enum-fields

### -field PerRequestExtension

Indicates the physical address of the SRB extension.


### -field DmaBuffer

Indicates the physical address of the DMA buffer.


### -field SRBDataBuffer

Indicates the physical address of a data buffer.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Strmini.h</dt>
</dl>
</td>
</tr>
</table>