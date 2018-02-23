---
UID: NE:ks.KSMETHOD_STREAMALLOCATOR
title: KSMETHOD_STREAMALLOCATOR
author: windows-driver-content
description: "."
old-location: stream\ksmethod_streamallocator.htm
old-project: stream
ms.assetid: 2CADC0BF-D8C0-48EC-8206-E1BD61DF4AD7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KSMETHOD_STREAMALLOCATOR, KSMETHOD_STREAMALLOCATOR_FREE, KSMETHOD_STREAMALLOCATOR_ALLOC, ks/KSMETHOD_STREAMALLOCATOR_FREE, ks/KSMETHOD_STREAMALLOCATOR_ALLOC, stream.ksmethod_streamallocator, KSMETHOD_STREAMALLOCATOR enumeration [Streaming Media Devices], ks/KSMETHOD_STREAMALLOCATOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KSMETHOD_STREAMALLOCATOR
product: Windows
targetos: Windows
req.typenames: KSMETHOD_STREAMALLOCATOR
---

# KSMETHOD_STREAMALLOCATOR Enumeration


## Syntax
````
typedef enum  { 
  KSMETHOD_STREAMALLOCATOR_ALLOC,
  KSMETHOD_STREAMALLOCATOR_FREE
} KSMETHOD_STREAMALLOCATOR;
````

## Constants

<table>
            
                <tr>
                    <td>KSMETHOD_STREAMALLOCATOR_ALLOC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSMETHOD_STREAMALLOCATOR_FREE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |