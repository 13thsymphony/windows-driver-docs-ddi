---
UID : NF:sensorsdef.SENSOR_PROPERTY_LIST_SIZE
title : SENSOR_PROPERTY_LIST_SIZE function
author : windows-driver-content
description : This function returns the size of the property list.
old-location : sensors\sensor_property_list_size.htm
old-project : sensors
ms.assetid : 17B53AAF-5027-4E45-ABAF-566771DDF1DE
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SENSOR_PROPERTY_LIST_SIZE function [Sensor Devices], sensorsdef/SENSOR_PROPERTY_LIST_SIZE, SENSOR_PROPERTY_LIST_SIZE, sensors.sensor_property_list_size
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sensorsdef.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SENSOR_STATE
req.product : Windows 10 or later.
---


# SENSOR_PROPERTY_LIST_SIZE function
This function returns the size of the property list.

## Syntax

````
FORCEINLINE ULONG SENSOR_PROPERTY_LIST_SIZE(
  _In_ ULONG Count
);
````

## Parameters

`Count`

The number of PROPERTYKEY elements.


## Return Value

The <b>SENSOR_PROPERTY_LIST_SIZE</b> function returns a ULONG value that represents the size of the property list.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sensorsdef.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |