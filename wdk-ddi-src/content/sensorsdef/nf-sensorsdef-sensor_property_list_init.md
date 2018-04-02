---
UID: NF:sensorsdef.SENSOR_PROPERTY_LIST_INIT
title: SENSOR_PROPERTY_LIST_INIT function
author: windows-driver-content
description: This function initializes a SENSOR_PROPERTY_LIST structure.
old-location: sensors\sensor_property_list_init.htm
old-project: sensors
ms.assetid: 5CCFA490-090E-4F24-A5E4-4BECA63EBA53
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SENSOR_PROPERTY_LIST_INIT, SENSOR_PROPERTY_LIST_INIT function [Sensor Devices], sensors.sensor_property_list_init, sensorsdef/SENSOR_PROPERTY_LIST_INIT
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
-	SENSOR_PROPERTY_LIST_INIT
product:
- Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---


# SENSOR_PROPERTY_LIST_INIT function
This function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a> structure.

## Syntax

```
void SENSOR_PROPERTY_LIST_INIT(
  PSENSOR_PROPERTY_LIST pPropertyList,
  ULONG                 PropertyListSize
);
```

## Parameters

`pPropertyList`

The list of PROPERTYKEY elements.

`PropertyListSize`

The size of pPropertyList.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sensorsdef.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>