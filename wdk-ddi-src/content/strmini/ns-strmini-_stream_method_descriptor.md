---
UID: NS:strmini._STREAM_METHOD_DESCRIPTOR
title: _STREAM_METHOD_DESCRIPTOR
author: windows-driver-content
description: .
old-location: stream\stream_method_descriptor.htm
old-project: stream
ms.assetid: 2C35EF9F-143C-4DE2-93D0-5BCF8AADF11B
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _STREAM_METHOD_DESCRIPTOR, *PSTREAM_METHOD_DESCRIPTOR, STREAM_METHOD_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_METHOD_DESCRIPTOR
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
req.typenames: *PSTREAM_METHOD_DESCRIPTOR, STREAM_METHOD_DESCRIPTOR
req.product: Windows 10 or later.
---

# _STREAM_METHOD_DESCRIPTOR structure



## -description




## -syntax

````
typedef struct _STREAM_METHOD_DESCRIPTOR {
  ULONG     MethodSetID;
  PKSMETHOD Method;
  PVOID     MethodInfo;
  LONG      MethodInputSize;
  LONG      MethodOutputSize;
} STREAM_METHOD_DESCRIPTOR, *PSTREAM_METHOD_DESCRIPTOR;
````


## -struct-fields

### -field MethodSetID


### -field Method


### -field MethodInfo


### -field MethodInputSize


### -field MethodOutputSize


## -remarks
