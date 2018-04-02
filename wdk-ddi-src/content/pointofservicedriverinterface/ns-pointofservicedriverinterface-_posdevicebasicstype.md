---
UID: NS:pointofservicedriverinterface._PosDeviceBasicsType
title: "_PosDeviceBasicsType"
author: windows-driver-content
description: This structure indicates the type of device, version, and recommended buffer size as specified by the driver.
old-location: pos\posdevicebasicstype.htm
old-project: pos
ms.assetid: 5f882f37-0554-48c0-b4a0-026d42452f56
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosDeviceBasicsType, PosDeviceBasicsType structure, _PosDeviceBasicsType, pointofservicedriverinterface/PosDeviceBasicsType, pos.posdevicebasicstype
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
-	PosDeviceBasicsType
product: Windows
targetos: Windows
req.typenames: PosDeviceBasicsType
---

# _PosDeviceBasicsType structure
This structure indicates the type of device, version, and recommended buffer size as specified by the driver.

## Syntax
```
typedef struct _PosDeviceBasicsType {
  UINT32        Version;
  PosDeviceType DeviceType;
  UINT32        RecommendedBufferSize;
} PosDeviceBasicsType;
```

## Members


`Version`

Contains the major and minor version of the POS driver interface. The top 16 bits contains the major version and the bottom 16 bits contains the minor version.

`DeviceType`

Indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772230">PosDeviceType</a> of the POS device (for example, a barcode scanner or a magnetic stripe reader).

`RecommendedBufferSize`

Indicates the size of the buffer that needs to be allocated to receive event data when calling <a href="http://go.microsoft.com/fwlink/p/?LinkId=314125">ReadFile</a> to retrieve events for this device


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |