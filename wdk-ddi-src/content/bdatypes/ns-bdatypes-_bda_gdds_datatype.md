---
UID: NS:bdatypes._BDA_GDDS_DATATYPE
title: "_BDA_GDDS_DATATYPE"
author: windows-driver-content
description: "."
old-location: stream\bda_gdds_datatype.htm
old-project: stream
ms.assetid: D2E6A110-EC0F-4753-BAF1-7A9F84ECDD35
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*P_BDA_GDDS_DATATYPE, BDA_GDDS_DATATYPE, BDA_GDDS_DATATYPE structure [Streaming Media Devices], P_BDA_GDDS_DATATYPE, P_BDA_GDDS_DATATYPE structure pointer [Streaming Media Devices], _BDA_GDDS_DATATYPE, bdatypes/BDA_GDDS_DATATYPE, bdatypes/P_BDA_GDDS_DATATYPE, stream.bda_gdds_datatype"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bdatypes.h
api_name:
-	BDA_GDDS_DATATYPE
product: Windows
targetos: Windows
req.typenames: BDA_GDDS_DATATYPE, *P_BDA_GDDS_DATATYPE
---

# _BDA_GDDS_DATATYPE structure


## Syntax
````
typedef struct _BDA_GDDS_DATATYPE {
  PBDARESULT lResult;
  GUID       uuidDataType;
} BDA_GDDS_DATATYPE, *P_BDA_GDDS_DATATYPE;
````

## Members


`lResult`



`uuidDataType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |