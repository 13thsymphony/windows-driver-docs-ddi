---
UID: NS:pointofservicedriverinterface._MSR_SUPPORTED_CARD_TYPES
title: "_MSR_SUPPORTED_CARD_TYPES"
author: windows-driver-content
description: This structure defines the types of magnetic stripe cards supported by the reader.
old-location: pos\msr_supported_card_types.htm
old-project: pos
ms.assetid: 57818ea9-f60b-4a37-9f42-613fb9cfaf36
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_MSR_SUPPORTED_CARD_TYPES, *PMSR_SUPPORTED_CARD_TYPES, PMSR_SUPPORTED_CARD_TYPES, pointofservicedriverinterface/PMSR_SUPPORTED_CARD_TYPES, MSR_SUPPORTED_CARD_TYPES structure, PMSR_SUPPORTED_CARD_TYPES structure pointer, pos.msr_supported_card_types, pointofservicedriverinterface/MSR_SUPPORTED_CARD_TYPES, MSR_SUPPORTED_CARD_TYPES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	MSR_SUPPORTED_CARD_TYPES
product: Windows
targetos: Windows
req.typenames: "*PMSR_SUPPORTED_CARD_TYPES, MSR_SUPPORTED_CARD_TYPES"
---

# _MSR_SUPPORTED_CARD_TYPES structure
This structure defines the types of magnetic stripe cards supported by the reader.

## Syntax
````
typedef struct _MSR_SUPPORTED_CARD_TYPES {
  unsigned char Count;
  unsigned int  CardTypes[MSR_CARD_TYPE_MAX_COUNT];
} MSR_SUPPORTED_CARD_TYPES, *PMSR_SUPPORTED_CARD_TYPES;
````

## Members


`CardTypes`

Magnetic stripe cards supported by the reader. The first <b>Count</b> members are valid.

`Count`

Count of supported magnetic stripe cards defined in <b>CardTypes[MSR_CARD_TYPE_MAX_COUNT]</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |