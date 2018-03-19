---
UID: NS:pointofservicedriverinterface._PosStatisticsHeader
title: "_PosStatisticsHeader"
author: windows-driver-content
description: This structure defines Unified Point of Service (UPOS) standard information about a device. This structure is the header for an incoming statistic.
old-location: pos\posstatisticsheader.htm
old-project: pos
ms.assetid: 75567f14-07fe-4861-9f78-e4de6d0bb023
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosStatisticsHeader, PosStatisticsHeader structure, _PosStatisticsHeader, pointofservicedriverinterface/PosStatisticsHeader, pos.posstatisticsheader
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
-	PosStatisticsHeader
product: Windows
targetos: Windows
req.typenames: PosStatisticsHeader
---

# _PosStatisticsHeader structure
This structure defines Unified Point of Service (UPOS) standard information about a device. This structure is the header for an incoming statistic.

## Syntax
````
typedef struct _PosStatisticsHeader {
  UINT32               EntryCount;
  PosDeviceInformation DeviceInformation;
  UINT32               DataLength;
} PosStatisticsHeader;
````

## Members


`EntryCount`

Indicates the number of statistics that follow this header.

`DeviceInformation`

A <a href="..\pointofservicecommontypes\ns-pointofservicecommontypes-_posdeviceinformation.md">PosDeviceInformation</a> structure that contains UPOS standard information about the device, such as its category, manufacturer, and firmware revision.

`DataLength`

Indicates the length, in bytes, of the <b>PosStatisticsHeader</b> and the buffer of <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posvaluestatisticsentry.md">PosValueStatisticsEntry</a> that follow this structure in memory.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |