---
UID: NS:mpiowmi._SetDSMCounters_IN
title: "_SetDSMCounters_IN"
author: windows-driver-content
description: The SetDSMCounters_IN structure is used to set the timer counters for a particular DSM.
old-location: storage\setdsmcounters_in.htm
old-project: storage
ms.assetid: fb8cebec-0cf8-4649-8b91-cd4f9935fac9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_SetDSMCounters_IN, PSetDSMCounters_IN structure pointer [Storage Devices], SetDSMCounters_IN, mpiowmi/PSetDSMCounters_IN, PSetDSMCounters_IN, storage.setdsmcounters_in, *PSetDSMCounters_IN, structs-scsibus_683362cd-cba9-41b8-9e46-9cf6a22fbbf5.xml, SetDSMCounters_IN structure [Storage Devices], mpiowmi/SetDSMCounters_IN"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	SetDSMCounters_IN
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# _SetDSMCounters_IN structure
The SetDSMCounters_IN structure is used to set the timer counters for a particular DSM.

## Syntax
````
typedef struct _SetDSMCounters_IN {
  ULONGLONG    DsmContext;
  DSM_COUNTERS DsmCounters;
} SetDSMCounters_IN, *PSetDSMCounters_IN;
````

## Members


`DsmContext`

A 64-bitfield that provides the DSM context.

`DsmCounters`

A structure of type DSM_COUNTERS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |