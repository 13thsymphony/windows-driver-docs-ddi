---
UID: NS:ks.KSMULTIPLE_ITEM
title: KSMULTIPLE_ITEM
author: windows-driver-content
description: The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries.
old-location: stream\ksmultiple_item.htm
old-project: stream
ms.assetid: f8a15cb0-92c5-4637-934e-021fa7969208
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSMULTIPLE_ITEM, KSMULTIPLE_ITEM, KSMULTIPLE_ITEM structure [Streaming Media Devices], PKSMULTIPLE_ITEM, PKSMULTIPLE_ITEM structure pointer [Streaming Media Devices], ks-struct_65ad7181-a002-4f51-8215-c82e7a1ee07c.xml, ks/KSMULTIPLE_ITEM, ks/PKSMULTIPLE_ITEM, stream.ksmultiple_item"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSMULTIPLE_ITEM
product: Windows
targetos: Windows
req.typenames: KSMULTIPLE_ITEM, *PKSMULTIPLE_ITEM
---

# KSMULTIPLE_ITEM structure
The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Count;
} KSMULTIPLE_ITEM, *PKSMULTIPLE_ITEM;
````

## Members


`Size`

Specifies the size in bytes of this header and the property data that follows.

`Count`

Specifies the number of buffers that follow this header.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/23c020e8-b778-4784-9dc0-21920557e1c1">Kernel Streaming Property Sets</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>