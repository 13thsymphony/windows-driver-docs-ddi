---
UID : NS:ntddvdeo._ENG_EVENT
title : _ENG_EVENT
author : windows-driver-content
description : The ENG_EVENT structure is reserved for system use.
old-location : display\eng_event.htm
old-project : display
ms.assetid : 8c785e23-5b80-4518-8a90-3f46e8ad9b1d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.eng_event, PENG_EVENT structure pointer [Display Devices], ntddvdeo/ENG_EVENT, ENG_EVENT structure [Display Devices], PENG_EVENT, *PEVENT, ntddvdeo/PENG_EVENT, _ENG_EVENT, ENG_EVENT, Video_Structs_a4ad3c78-3ef4-42b2-9640-ef253a74637b.xml, *PENG_EVENT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddvdeo.h
req.include-header : Ntddvdeo.h
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
req.typenames : ENG_EVENT, *PENG_EVENT, *PEVENT
---

# _ENG_EVENT structure
The ENG_EVENT structure is reserved for system use.

## Syntax
````
typedef struct _ENG_EVENT {
  PVOID pKEvent;
  ULONG fFlags;
} ENG_EVENT, *PENG_EVENT;
````

## Members


`fFlags`

Reserved for system use.

`pKEvent`

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |