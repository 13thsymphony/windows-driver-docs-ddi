---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
title: SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function
author: windows-driver-content
description: This function calculates the number of SENSOR_VALUE_PAIR elements in a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_calculate_max_count.htm
old-project: sensors
ms.assetid: 56C94717-41FF-44AA-BC99-1ECE4A407A38
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT, SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function [Sensor Devices], sensors.sensor_collection_list_calculate_max_count, sensorsdef/SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
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
-	SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
product:
- Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---


# SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function
This function calculates the number of <a href="https://msdn.microsoft.com/library/windows/hardware/dn946708">SENSOR_VALUE_PAIR</a> elements in a <a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a> structure.

## Syntax

```
ULONG SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT(
  PSENSOR_COLLECTION_LIST pCollectionList
);
```

## Parameters

`pCollectionList`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a> structure.


## Return Value

The <b>SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</b> function returns a ULONG value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorsdef.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957092">SENSOR_COLLECTION_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946708">SENSOR_VALUE_PAIR</a>