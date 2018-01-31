---
UID : NS:wiamicro._RANGEVALUE
title : "_RANGEVALUE"
author : windows-driver-content
description : The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter.
old-location : image\rangevalue.htm
old-project : image
ms.assetid : 18322d1f-9fc9-43f0-925e-616731845792
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : MicroDrv_8569166c-7a4e-47eb-beed-57c715102258.xml, wiamicro/RANGEVALUE, RANGEVALUE structure [Imaging Devices], _RANGEVALUE, PRANGEVALUE, RANGEVALUE, PRANGEVALUE structure pointer [Imaging Devices], *PRANGEVALUE, wiamicro/PRANGEVALUE, image.rangevalue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wiamicro.h
req.include-header : Wiamicro.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.typenames : "*PRANGEVALUE, RANGEVALUE"
req.product : Windows 10 or later.
---

# _RANGEVALUE structure
The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter.

## Syntax
````
typedef struct _RANGEVALUE {
  LONG lMin;
  LONG lMax;
  LONG lStep;
} RANGEVALUE, *PRANGEVALUE;
````

## Members


`lMax`

Specifies the maximum value for a parameter.

`lMin`

Specifies the minimum value for a parameter.

`lStep`

Specifies the step value for a parameter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamicro.h (include Wiamicro.h) |