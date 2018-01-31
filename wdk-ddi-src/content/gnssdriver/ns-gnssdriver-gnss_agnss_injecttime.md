---
UID : NS:gnssdriver.GNSS_AGNSS_INJECTTIME
title : GNSS_AGNSS_INJECTTIME
author : windows-driver-content
description : This structure defines the format for AGNSS time injection.
old-location : sensors\gnss_agnss_injecttime.htm
old-project : sensors
ms.assetid : 05BCC40C-E542-4BE8-9FD7-F0D25C3B8C7C
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PGNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME, GNSS_AGNSS_INJECTTIME, gnssdriver/PGNSS_AGNSS_INJECTTIME, gnssdriver/GNSS_AGNSS_INJECTTIME, sensors.gnss_agnss_injecttime, GNSS_AGNSS_INJECTTIME structure [Sensor Devices], PGNSS_AGNSS_INJECTTIME structure pointer [Sensor Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : GNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME
---

# GNSS_AGNSS_INJECTTIME structure
This structure defines the format for AGNSS time injection.

## Syntax
````
typedef struct {
  ULONG    Size;
  ULONG    Version;
  FILETIME UtcTime;
  ULONG    TimeUncertainty;
} GNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME;
````

## Members


`Size`

Structure size.

`TimeUncertainty`

Uncertainty in milliseconds.

`UtcTime`

UTC time.

`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |