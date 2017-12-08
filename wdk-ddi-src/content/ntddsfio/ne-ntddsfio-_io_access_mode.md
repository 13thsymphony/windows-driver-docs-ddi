---
UID: NE.ntddsfio._IO_ACCESS_MODE
title: _IO_ACCESS_MODE
author: windows-driver-content
description: Defines the types of access mode for Scheduled File I/O (SFIO).
old-location: kernel\io_access_mode.htm
old-project: kernel
ms.assetid: E48BDF14-5B56-45AF-9DD2-F019C8B7D7E5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _IO_ACCESS_MODE, IO_ACCESS_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddsfio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_ACCESS_MODE
req.alt-loc: Ntddsfio.h
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
---

# _IO_ACCESS_MODE enumeration



## -description
Defines the types of access mode for Scheduled File I/O (SFIO).


## -syntax

````
typedef enum _IO_ACCESS_MODE { 
  SequentialAccess,
  RandomAccess
} IO_ACCESS_MODE;
````


## -enum-fields

### -field SequentialAccess

Indicates that the input/output will be sent down in a sequential order.

### -field RandomAccess

Indicates that the input/output might not be in a predictable order.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddsfio.h</dt>
</dl>
</td>
</tr>
</table>