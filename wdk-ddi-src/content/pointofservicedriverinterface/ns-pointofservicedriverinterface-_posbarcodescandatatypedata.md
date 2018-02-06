---
UID: NS:pointofservicedriverinterface._PosBarcodeScanDataTypeData
title: "_PosBarcodeScanDataTypeData"
author: windows-driver-content
description: This structure describes a buffer of barcode symbologies supported by the driver.
old-location: pos\posbarcodescandatatypedata.htm
old-project: pos
ms.assetid: 1b6fcad3-a6a0-4180-8e36-ae4e597b4eb0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_PosBarcodeScanDataTypeData, PosBarcodeScanDataTypeData, pointofservicedriverinterface/PosBarcodeScanDataTypeData, pos.posbarcodescandatatypedata, PosBarcodeScanDataTypeData structure"
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
-	PosBarcodeScanDataTypeData
product: Windows
targetos: Windows
req.typenames: PosBarcodeScanDataTypeData
---

# _PosBarcodeScanDataTypeData structure
This structure describes a buffer of barcode symbologies supported by the driver.

## Syntax
````
typedef struct _PosBarcodeScanDataTypeData {
  UINT32 dataLengthInBytes;
  UINT32 scanDataTypes_0;
} PosBarcodeScanDataTypeData;
````

## Members


`dataLengthInBytes`

The size of the buffer that contains the symbologies, including the size of the <b>PosBarcodeScanDataTypeData</b> structure.

`scanDataTypes_0`

The start of the DWORD array of symbologies.

## Remarks
Each symbology in the buffer is represented by a DWORD. The size of the array of symboligies that scanDataTypes_0 points to is <code>scanDataTypes_0/sizeof(UINT32) - 1;</code>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |