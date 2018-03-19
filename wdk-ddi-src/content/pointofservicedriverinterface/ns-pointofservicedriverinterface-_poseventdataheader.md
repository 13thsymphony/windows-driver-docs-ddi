---
UID: NS:pointofservicedriverinterface._PosEventDataHeader
title: "_PosEventDataHeader"
author: windows-driver-content
description: This structure describes the scanned image data that is passed to the BarcodeScannerImagePreviewReceived event.
old-location: pos\posbarcodescannerimageprevieweventdata.htm
old-project: pos
ms.assetid: dc542e81-9078-4e14-8c8d-9cfaeb5b5495
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosBarcodeScannerImagePreviewEventData, PosBarcodeScannerImagePreviewEventData structure, PosEventDataHeader, PosEventDataHeader structure, _PosEventDataHeader, pointofservicedriverinterface/PosBarcodeScannerImagePreviewEventData, pointofservicedriverinterface/PosEventDataHeader, pos.posbarcodescannerimageprevieweventdata
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PointOfServiceDriverInterface.h
api_name:
-	PosEventDataHeader
product: Windows
targetos: Windows
req.typenames: PosEventDataHeader, PosBarcodeScannerImagePreviewEventData
---

# _PosEventDataHeader structure
This structure describes the scanned image data that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event.

## Syntax
````
typedef struct _PosEventDataHeader {
  PosEventType EventType;
  UINT32       DataLength;
} PosEventDataHeader, PosBarcodeScannerImagePreviewEventData;
````

## Members


`EventType`

The type of event. For the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event the value of this field is <b>BarcodeScannerImagePreviewReceived</b>.

`DataLength`

The length, in bytes, of the image preview data.

## Remarks
The image preview bitmap data immediately follows after this structure in memory for <i>DataLength</i> bytes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |