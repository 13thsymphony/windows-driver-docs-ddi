---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_INIT
title: SENSOR_COLLECTION_LIST_INIT function
author: windows-driver-content
description: This function initializes a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_init.htm
old-project: sensors
ms.assetid: 50860DA0-D42C-4ACB-A574-C0DEA85713BD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensorsdef/SENSOR_COLLECTION_LIST_INIT, sensors.sensor_collection_list_init, SENSOR_COLLECTION_LIST_INIT function [Sensor Devices], SENSOR_COLLECTION_LIST_INIT
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Sensorsdef.h
apiname:
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
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SENSOR_COLLECTION_LIST_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>