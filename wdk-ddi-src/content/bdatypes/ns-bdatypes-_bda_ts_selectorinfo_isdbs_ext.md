---
UID : NS:bdatypes._BDA_TS_SELECTORINFO_ISDBS_EXT
title : _BDA_TS_SELECTORINFO_ISDBS_EXT
author : windows-driver-content
description : .
old-location : stream\bda_ts_selectorinfo_isdbs_ext.htm
old-project : stream
ms.assetid : F56D4984-B159-4068-8081-3E2457E50998
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_TS_SELECTORINFO_ISDBS_EXT, BDA_TS_SELECTORINFO_ISDBS_EXT, *PBDA_TS_SELECTORINFO_ISDBS_EXT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BDA_TS_SELECTORINFO_ISDBS_EXT
req.alt-loc : Bdatypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : BDA_TS_SELECTORINFO_ISDBS_EXT, *PBDA_TS_SELECTORINFO_ISDBS_EXT
---

# _BDA_TS_SELECTORINFO_ISDBS_EXT structure


## Syntax
````
typedef struct _BDA_TS_SELECTORINFO_ISDBS_EXT {
  BYTE bTMCC[48];
} BDA_TS_SELECTORINFO_ISDBS_EXT, *PBDA_TS_SELECTORINFO_ISDBS_EXT;
````

## Members

        
            `bTMCC`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |