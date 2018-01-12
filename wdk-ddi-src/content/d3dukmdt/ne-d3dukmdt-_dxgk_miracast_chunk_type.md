---
UID: NE:d3dukmdt._DXGK_MIRACAST_CHUNK_TYPE
title: _DXGK_MIRACAST_CHUNK_TYPE
author: windows-driver-content
description: Specifies the types of wireless display (Miracast) chunk info that is to be processed.
old-location: display\dxgk_miracast_chunk_type.htm
old-project: display
ms.assetid: 6C44EFD1-9366-4119-945E-688176D9F5D5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_MIRACAST_CHUNK_TYPE, DXGK_MIRACAST_CHUNK_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MIRACAST_CHUNK_TYPE
req.alt-loc: D3dukmdt.h
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
req.typenames: DXGK_MIRACAST_CHUNK_TYPE
---

# _DXGK_MIRACAST_CHUNK_TYPE enumeration



## -description
Specifies the types of wireless display (Miracast) chunk info that is to be processed.



## -syntax

````
typedef enum _DXGK_MIRACAST_CHUNK_TYPE { 
  DXGK_MIRACAST_CHUNK_TYPE_UNKNOWN                  = 0,
  DXGK_MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE   = 1,
  DXGK_MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE          = 2,
  DXGK_MIRACAST_CHUNK_TYPE_FRAME_START              = 3,
  DXGK_MIRACAST_CHUNK_TYPE_FRAME_DROPPED            = 4,
  DXGK_MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1  = 0x80000000,
  DXGK_MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2  = 0x80000001
} DXGK_MIRACAST_CHUNK_TYPE;
````


## -enum-fields

### -field DXGK_MIRACAST_CHUNK_TYPE_UNKNOWN

An unknown or undefined chunk type.


### -field DXGK_MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE

Color conversion has completed on the chunk.


### -field DXGK_MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE

Encoding has completed on the chunk.


### -field DXGK_MIRACAST_CHUNK_TYPE_FRAME_START

The chunk is at the start of the Wi-Fi frame.


### -field DXGK_MIRACAST_CHUNK_TYPE_FRAME_DROPPED

The chunk is in a dropped Wi-Fi frame.


### -field DXGK_MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1

Encoding is driver-defined, of type 1.


### -field DXGK_MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2

Encoding is driver-defined, of type 2.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dukmdt.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>