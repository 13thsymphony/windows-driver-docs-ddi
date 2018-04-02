---
UID: NF:ntifs.IoIsValidNameGraftingBuffer
title: IoIsValidNameGraftingBuffer function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\ioisvalidnamegraftingbuffer.htm
old-project: ifsk
ms.assetid: 9680724b-15fb-4d46-9fd1-175fa1b71c73
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoIsValidNameGraftingBuffer, IoIsValidNameGraftingBuffer function [Installable File System Drivers], ifsk.ioisvalidnamegraftingbuffer, ioref_10a2f83c-101f-47b3-beca-c708a0749d4d.xml, ntifs/IoIsValidNameGraftingBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	ntifs.h
api_name:
-	IoIsValidNameGraftingBuffer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoIsValidNameGraftingBuffer function
The <b>IoIsValidNameGraftingBuffer</b> routine is reserved for system use.

## Syntax

```
NTKERNELAPI BOOLEAN IoIsValidNameGraftingBuffer(
  PIRP                 Irp,
  PREPARSE_DATA_BUFFER ReparseBuffer
);
```

## Parameters

`Irp`

TBD

`ReparseBuffer`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |