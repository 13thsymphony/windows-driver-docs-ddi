---
UID: NS:pointofservicedriverinterface._PosStatusUpdatedEventData
title: "_PosStatusUpdatedEventData"
author: windows-driver-content
description: This structure contains data passed to the StatusUpdated event.
old-location: pos\posstatusupdatedeventdata.htm
old-project: pos
ms.assetid: 382e5441-dce1-428b-90af-d57b5f930abb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_PosStatusUpdatedEventData, PosStatusUpdatedEventData, pos.posstatusupdatedeventdata, pointofservicedriverinterface/PosStatusUpdatedEventData, PosStatusUpdatedEventData structure"
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
-	PosStatusUpdatedEventData
product: Windows
targetos: Windows
req.typenames: PosStatusUpdatedEventData
---

# _PosStatusUpdatedEventData structure
This structure contains data passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790040">StatusUpdated</a> event.

## Syntax
````
typedef struct _PosStatusUpdatedEventData {
  PosEventDataHeader Header;
  UINT32             Status;
  UINT32             ExtendedStatus;
} PosStatusUpdatedEventData;
````

## Members


`ExtendedStatus`

Indicates a driver-specific value intended to be used by the vendor for diagnostic purposes.

`Header`

A <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_poseventdataheader.md">PosEventDataHeader</a> structure that contains information about the event that was raised and the amount of memory, in bytes, that this event data uses.

`Status`

Indicates a device-specific enumeration value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |