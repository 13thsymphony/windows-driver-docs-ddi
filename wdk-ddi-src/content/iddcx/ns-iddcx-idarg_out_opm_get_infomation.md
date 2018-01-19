---
UID : NS:iddcx.IDARG_OUT_OPM_GET_INFOMATION
title : IDARG_OUT_OPM_GET_INFOMATION
author : windows-driver-content
description : Gives the OPM information that was requested.
old-location : display\idarg_out_opm_get_infomation.htm
old-project : display
ms.assetid : 7c51b228-480d-4e19-aa70-4fcc44ffae16
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : IDARG_OUT_OPM_GET_INFOMATION,
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
req.alt-api : IDARG_OUT_OPM_GET_INFOMATION
req.alt-loc : iddcx.h
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
req.typenames : 
---

# IDARG_OUT_OPM_GET_INFOMATION structure
Gives the OPM information that was requested.

## Syntax
````
typedef struct IDARG_OUT_OPM_GET_INFOMATION {
  IDDCX_OPM_REQUESTED_INFORMATION RequestedInformation;
} IDARG_OUT_OPM_GET_INFOMATION, *IDARG_OUT_OPM_GET_INFOMATION;
````

## Members

        
            `RequestedInformation`

            [out] The OPM information that was requested.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |