---
UID: NS:d3dumddi._D3DDDIRANGE
title: "_D3DDDIRANGE"
author: windows-driver-content
description: Specifies a range of memory within a buffer.
old-location: display\d3dddirange.htm
old-project: display
ms.assetid: 3A64DB04-EDAE-419C-947B-67201ECA8068
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIRANGE structure [Display Devices], d3dumddi/D3DDDIRANGE, _D3DDDIRANGE, D3DDDIRANGE, display.d3dddirange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDIRANGE
product: Windows
targetos: Windows
req.typenames: D3DDDIRANGE
---

# _D3DDDIRANGE structure
Specifies a range of memory within a buffer.

## Syntax
````
typedef struct _D3DDDIRANGE {
  UINT Offset;
  UINT Size;
} D3DDDIRANGE;
````

## Members


`Offset`

An offset, in bytes, from the start of the buffer.

`Size`

The size, in bytes, of a block of memory that begins at the buffer location specified by the <b>Offset</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |