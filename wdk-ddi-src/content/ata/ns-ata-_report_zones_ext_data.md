---
UID : NS:ata._REPORT_ZONES_EXT_DATA
title : _REPORT_ZONES_EXT_DATA
author : windows-driver-content
description : Note  This structure is for internal use only and should not be called from your code. .
old-location : storage\report_zones_ext_data.htm
old-project : storage
ms.assetid : 0c6b4b7c-548d-42c0-af9b-cf0d65bf2e45
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PREPORT_ZONES_EXT_DATA, _REPORT_ZONES_EXT_DATA, ata/PREPORT_ZONES_EXT_DATA, REPORT_ZONES_EXT_DATA, storage.report_zones_ext_data, ata/REPORT_ZONES_EXT_DATA, PREPORT_ZONES_EXT_DATA structure pointer [Storage Devices], REPORT_ZONES_EXT_DATA structure [Storage Devices], *PREPORT_ZONES_EXT_DATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ata.h
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
req.typenames : "*PREPORT_ZONES_EXT_DATA, REPORT_ZONES_EXT_DATA"
---

# _REPORT_ZONES_EXT_DATA structure
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>

## Syntax
````
typedef struct _REPORT_ZONES_EXT_DATA {
  ULONG     ZoneListLength;
  UCHAR     SAME  :4;
  UCHAR     Reserved0  :4;
  UCHAR     Reserved1[3];
  ULONGLONG MaxLBA  :48;
  ULONGLONG Reserved2  :16;
  UCHAR     Reserved3[48];
} REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA;
````

## Members


`MaxLBA`

N/A

`Reserved0`

Reserved for future use.

`Reserved1`

Reserved for future use.

`Reserved2`

Reserved for future use.

`Reserved3`

Reserved for future use.

`SAME`

N/A

`ZoneListLength`

N/A


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ata.h |