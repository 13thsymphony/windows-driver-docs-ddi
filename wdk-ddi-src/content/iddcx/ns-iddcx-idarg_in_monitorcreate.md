---
UID : NS:iddcx.IDARG_IN_MONITORCREATE
title : IDARG_IN_MONITORCREATE
author : windows-driver-content
description : Gives information about the monitor object that will be created.
old-location : display\idarg_in_monitorcreate.htm
old-project : display
ms.assetid : 0de9686f-69e6-4aac-8f58-9e61bcfe3827
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.idarg_in_monitorcreate, iddcx/IDARG_IN_MONITORCREATE, IDARG_IN_MONITORCREATE, IDARG_IN_MONITORCREATE structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iddcx.h
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
req.typenames : 
---

# IDARG_IN_MONITORCREATE structure
Gives information about the monitor object that will be created.

## Syntax
````
typedef struct IDARG_IN_MONITORCREATE {
  PWDF_OBJECT_ATTRIBUTES ObjectAttributes;
  IDDCX_MONITOR_INFO*    pMonitorInfo;
} IDARG_IN_MONITORCREATE, *IDARG_IN_MONITORCREATE;
````

## Members


`ObjectAttributes`

Indicates object attributes for the monitor.

`pMonitorInfo`

[in] Pointer to the information about this monitor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |