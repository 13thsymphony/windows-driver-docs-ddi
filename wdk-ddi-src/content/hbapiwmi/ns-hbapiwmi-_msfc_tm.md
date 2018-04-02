---
UID: NS:hbapiwmi._MSFC_TM
title: "_MSFC_TM"
author: windows-driver-content
description: The MSFC_TM structure is used by WMI providers to timestamp events.
old-location: storage\msfc_tm.htm
old-project: storage
ms.assetid: 7e27f53f-350e-4315-9de6-60835bddcbfb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_TM, MSFC_TM, MSFC_TM structure [Storage Devices], PMSFC_TM, PMSFC_TM structure pointer [Storage Devices], _MSFC_TM, hbapiwmi/MSFC_TM, hbapiwmi/PMSFC_TM, storage.msfc_tm, structs-Fibre_5cca5127-bbcc-4a2f-9ad2-2daeecac1448.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
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
-	hbapiwmi.h
api_name:
-	MSFC_TM
product: Windows
targetos: Windows
req.typenames: MSFC_TM, *PMSFC_TM
---

# _MSFC_TM structure
The MSFC_TM structure is used by WMI providers to timestamp events.

## Syntax
```
typedef struct _MSFC_TM {
  ULONG tm_sec;
  ULONG tm_min;
  ULONG tm_hour;
  ULONG tm_mday;
  ULONG tm_mon;
  ULONG tm_year;
  ULONG tm_wday;
  ULONG tm_yday;
  ULONG tm_isdst;
} MSFC_TM, *PMSFC_TM;
```

## Members


`tm_sec`

Indicates the number of seconds past the minute. This member must have a value between 0 and 59.

`tm_min`

Indicates the number of minutes after the hour. This member must have a value between 0 and 59.

`tm_hour`

Indicates the number of hours since midnight. This member must have a value between 0 and 23.

`tm_mday`

Indicates the day of the month. This member must have a value between 1 and 31.

`tm_mon`

Indicates the number of months since January. This member must have a value between 0 and 11.

`tm_year`

Indicates the number of years since 1900.

`tm_wday`

Indicates the number of days since Sunday. This member must have a value between 0 and 6.

`tm_yday`

Indicates the number of days since January 1. This member must have a value between 0 and 365.

`tm_isdst`

Indicates when <b>TRUE</b> that the time stamp complies with daylight savings time. When <b>FALSE</b>, indicates that the timestamp does not comply with daylight savings time.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562965">MSFC_TM WMI Class</a>