---
UID: NS:ntddstor._STORAGE_TEMPERATURE_INFO
title: "_STORAGE_TEMPERATURE_INFO"
author: windows-driver-content
description: Describes device temperature data. Returned as part of STORAGE_TEMPERATURE_DATA_DESCRIPTOR when querying for temperature data with an IOCTL_STORAGE_QUERY_PROPERTY request.
old-location: storage\storage_temperature_info.htm
old-project: storage
ms.assetid: 1B7C68BF-78AE-4427-B5DC-E388CB5FAC0C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO, PSTORAGE_TEMPERATURE_INFO structure pointer [Storage Devices], STORAGE_TEMPERATURE_INFO, STORAGE_TEMPERATURE_INFO structure [Storage Devices], _STORAGE_TEMPERATURE_INFO, ntddstor/PSTORAGE_TEMPERATURE_INFO, ntddstor/STORAGE_TEMPERATURE_INFO, storage.storage_temperature_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddstor.h
api_name:
-	STORAGE_TEMPERATURE_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_TEMPERATURE_INFO, *PSTORAGE_TEMPERATURE_INFO
---

# _STORAGE_TEMPERATURE_INFO structure
Describes  device temperature data. Returned as part of <a href="https://msdn.microsoft.com/library/windows/hardware/mt651017">STORAGE_TEMPERATURE_DATA_DESCRIPTOR</a> when querying for temperature data with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request.

## Syntax
```
typedef struct _STORAGE_TEMPERATURE_INFO {
  USHORT  Index;
  SHORT   Temperature;
  SHORT   OverThreshold;
  SHORT   UnderThreshold;
  BOOLEAN OverThresholdChangable;
  BOOLEAN UnderThresholdChangable;
  BOOLEAN EventGenerated;
  UCHAR   Reserved0;
  ULONG   Reserved1;
} *PSTORAGE_TEMPERATURE_INFO, STORAGE_TEMPERATURE_INFO;
```

## Members


`Index`

Identifies the instance of temperature information. Starts from 0. Index 0 may indicate a composite value.

`Temperature`

A signed value that indicates the current temperature, in degrees Celsius.

`OverThreshold`

A signed value that specifies the maximum temperature within the desired threshold, in degrees Celsius.

`UnderThreshold`

A signed value that specifies the minimum temperature within the desired threshold, in degrees Celsius.

`OverThresholdChangable`

Indicates if <i>OverThreshold</i> can be changed by using <a href="https://msdn.microsoft.com/library/windows/hardware/mt650982">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.

`UnderThresholdChangable`

Indicates if <i>UnderThreshold</i> can be changed by using <a href="https://msdn.microsoft.com/library/windows/hardware/mt650982">IOCTL_STORAGE_SET_TEMPERATURE_THRESHOLD</a>.

`EventGenerated`

Indicates if a notification will be generated when the current temperature crosses a threshold.

`Reserved0`

Reserved for future use.

`Reserved1`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566996">STORAGE_PROPERTY_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566997">STORAGE_PROPERTY_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt651018">STORAGE_TEMPERATURE_INFO</a>