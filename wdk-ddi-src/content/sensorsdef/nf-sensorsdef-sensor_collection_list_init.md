---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_INIT
title: SENSOR_COLLECTION_LIST_INIT function
author: windows-driver-content
description: This function initializes a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_init.htm
old-project: sensors
ms.assetid: 50860DA0-D42C-4ACB-A574-C0DEA85713BD
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SENSOR_COLLECTION_LIST_INIT, SENSOR_COLLECTION_LIST_INIT function [Sensor Devices], sensors.sensor_collection_list_init, sensorsdef/SENSOR_COLLECTION_LIST_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorsdef.h
req.include-header: 
req.target-type: Desktop
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
-	Sensorsdef.h
api_name:
-	SENSOR_COLLECTION_LIST_INIT
product: Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---


# SENSOR_COLLECTION_LIST_INIT function
This function initializes a <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a> structure.

## Syntax

````
FORCEINLINE VOID SENSOR_COLLECTION_LIST_INIT(
  _Out_ writes_bytes_(CollectionListSize) PSENSOR_COLLECTION_LIST                       pCollectionList,
  _In_  _Pre_satisfies_(SENSOR_COLLECTION_LIST_HEADER_SIZE <= CollectionListSize) ULONG CollectionListSize
);
````

## Parameters

`pCollectionList`

A pointer to a <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.

`CollectionListSize`

The size of the <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorsdef.h |

## See Also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>