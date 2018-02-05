---
UID : NS:iddcx.IDDCX_OPM_REQUESTED_INFORMATION
title : IDDCX_OPM_REQUESTED_INFORMATION
author : windows-driver-content
description : Gives the information requested from the OPM.
old-location : display\iddcx_opm_requested_information.htm
old-project : display
ms.assetid : 0e8c49b2-1c36-432b-aba9-bc6a739ee04d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : IDDCX_OPM_REQUESTED_INFORMATION, iddcx/IDDCX_OPM_REQUESTED_INFORMATION, IDDCX_OPM_REQUESTED_INFORMATION structure [Display Devices], display.iddcx_opm_requested_information
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

# IDDCX_OPM_REQUESTED_INFORMATION structure
Gives the information requested from the OPM.

## Syntax
````
typedef struct IDDCX_OPM_REQUESTED_INFORMATION {
  UINT                      Size;
  OPM_REQUESTED_INFORMATION RequestedInformation;
} IDDCX_OPM_REQUESTED_INFORMATION, *IDDCX_OPM_REQUESTED_INFORMATION;
````

## Members


`RequestedInformation`

The information that was requested.

`Size`

Total size of the structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |