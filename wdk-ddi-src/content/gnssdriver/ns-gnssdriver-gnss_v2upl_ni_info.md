---
UID : NS:gnssdriver.GNSS_V2UPL_NI_INFO
title : GNSS_V2UPL_NI_INFO
author : windows-driver-content
description : This structure contains V2UPL NI information.
old-location : sensors\gnss_v2upl_ni_info.htm
old-project : sensors
ms.assetid : 884C8141-2A15-4BAE-8A5C-73355BD84D53
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO
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
req.alt-api : GNSS_V2UPL_NI_INFO
req.alt-loc : gnssdriver.h
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
req.typenames : "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO"
---

# GNSS_V2UPL_NI_INFO structure
This structure contains V2UPL NI information.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR RequestorId[MAX_PATH];
} GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO;
````

## Members

        
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