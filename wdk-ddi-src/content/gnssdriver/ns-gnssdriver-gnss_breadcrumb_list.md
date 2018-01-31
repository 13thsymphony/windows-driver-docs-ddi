---
UID : NS:gnssdriver.GNSS_BREADCRUMB_LIST
title : GNSS_BREADCRUMB_LIST
author : windows-driver-content
description : This structure contains the response to an IOCTL_GNSS_POP_BREADCRUMBS.
old-location : sensors\gnss_breadcrumb_list.htm
old-project : sensors
ms.assetid : 40C11C4B-2FFE-452F-AA08-2BCD4B6A4F7F
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PGNSS_BREADCRUMB_LIST structure pointer [Sensor Devices], gnssdriver/PGNSS_BREADCRUMB_LIST, *PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST structure [Sensor Devices], sensors.gnss_breadcrumb_list, PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST, gnssdriver/GNSS_BREADCRUMB_LIST
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
req.typenames : "*PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST"
---

# GNSS_BREADCRUMB_LIST structure
This structure contains the response to an <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_pop_breadcrumbs.md">IOCTL_GNSS_POP_BREADCRUMBS</a>.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG NumCrumbs;
  union {
    GNSS_BREADCRUMB_V1  v1[50];
  };
} GNSS_BREADCRUMB_LIST, *PGNSS_BREADCRUMB_LIST;
````

## Members


`NumCrumbs`

The number of breadcrumbs in the <b>IOCTL_GNSS_POP_BREADCRUMBS</b> response.

`Size`

Structure size.

`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |