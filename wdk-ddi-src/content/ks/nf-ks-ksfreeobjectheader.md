---
UID: NF:ks.KsFreeObjectHeader
title: KsFreeObjectHeader function
author: windows-driver-content
description: The KsFreeObjectHeader function cleans up and frees a previously allocated object header.
old-location: stream\ksfreeobjectheader.htm
old-project: stream
ms.assetid: 59ca5035-f4d8-4a9c-a298-c8dca604f4db
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFreeObjectHeader, KsFreeObjectHeader function [Streaming Media Devices], ks/KsFreeObjectHeader, ksfunc_11097907-6879-43bb-879b-b74eb13d6109.xml, stream.ksfreeobjectheader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFreeObjectHeader
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsFreeObjectHeader function
The <b>KsFreeObjectHeader</b> function cleans up and frees a previously allocated object header.

## Syntax

```
KSDDKAPI VOID KsFreeObjectHeader(
  KSOBJECT_HEADER Header
);
```

## Parameters

`Header`

Points to the object header to free.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560972">KsAllocateObjectHeader</a>