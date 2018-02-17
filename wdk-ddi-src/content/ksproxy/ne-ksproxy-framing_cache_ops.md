---
UID: NE:ksproxy.FRAMING_CACHE_OPS
title: FRAMING_CACHE_OPS
author: windows-driver-content
description: "."
old-location: stream\framing_cache_ops.htm
old-project: stream
ms.assetid: EA496897-7D5A-43A8-A61E-34E986288E8B
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: Framing_Cache_ReadOrig, ksproxy/Framing_Cache_Write, Framing_Cache_Update, Framing_Cache_ReadLast, ksproxy/Framing_Cache_ReadLast, FRAMING_CACHE_OPS, stream.framing_cache_ops, ksproxy/FRAMING_CACHE_OPS, Framing_Cache_Write, ksproxy/Framing_Cache_Update, FRAMING_CACHE_OPS enumeration [Streaming Media Devices], ksproxy/Framing_Cache_ReadOrig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksproxy.h
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
-	Ksproxy.h
apiname:
-	FRAMING_CACHE_OPS
product: Windows
targetos: Windows
req.typenames: FRAMING_CACHE_OPS
---

# FRAMING_CACHE_OPS Enumeration


## Syntax
````
typedef enum  { 
  Framing_Cache_Update,
  Framing_Cache_ReadLast,
  Framing_Cache_ReadOrig,
  Framing_Cache_Write
} FRAMING_CACHE_OPS;
````

## Constants

<table>
            
                <tr>
                    <td>Framing_Cache_ReadLast</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>Framing_Cache_ReadOrig</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>Framing_Cache_Update</td>
                    <td>Specifies a request to bypass the cache when reading or writing.</td>
                </tr>
            
                <tr>
                    <td>Framing_Cache_Write</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksproxy.h |