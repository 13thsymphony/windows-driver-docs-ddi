---
UID: NS:mpiowmi._ClearPathHealthCounters_IN
title: "_ClearPathHealthCounters_IN"
author: windows-driver-content
description: The ClearPathHealthCounters_IN structure is used to provide an input parameter to the ClearPathHealthCounters method.
old-location: storage\clearpathhealthcounters_in.htm
old-project: storage
ms.assetid: 12c4462a-886b-4446-ace4-128af0af5dc0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PClearPathHealthCounters_IN, ClearPathHealthCounters_IN, ClearPathHealthCounters_IN structure [Storage Devices], PClearPathHealthCounters_IN, PClearPathHealthCounters_IN structure pointer [Storage Devices], _ClearPathHealthCounters_IN, mpiowmi/ClearPathHealthCounters_IN, mpiowmi/PClearPathHealthCounters_IN, storage.clearpathhealthcounters_in, structs-scsibus_c1039fbb-d682-4fe8-a1ee-8fe7f7a0d1fc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
-	mpiowmi.h
api_name:
-	ClearPathHealthCounters_IN
product: Windows
targetos: Windows
req.typenames: ClearPathHealthCounters_IN, *PClearPathHealthCounters_IN
---

# _ClearPathHealthCounters_IN structure
The ClearPathHealthCounters_IN structure is used to provide an input parameter to the ClearPathHealthCounters method.

## Syntax
````
typedef struct _ClearPathHealthCounters_IN {
  ULONGLONG PathID;
} ClearPathHealthCounters_IN, *PClearPathHealthCounters_IN;
````

## Members


`PathID`

A 64-bitfield that specifies the path that is associated with the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |