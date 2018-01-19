---
UID : NS:ntddrilapitypes.RILNITZINFO_V2
title : RILNITZINFO_V2
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilnitzinfo_v2.htm
old-project : netvista
ms.assetid : 31980e7f-b767-4f63-9dc6-efce582d84ea
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILNITZINFO_V2, RILNITZINFO_V2, *LPRILNITZINFO, *LPRILNITZINFO_V2, RILNITZINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILNITZINFO_V2
req.alt-loc : ntddrilapitypes.h
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
req.typenames : RILNITZINFO_V2, *LPRILNITZINFO, *LPRILNITZINFO_V2, RILNITZINFO
---

# RILNITZINFO_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILNITZINFO_V2 {
  DWORD          cbSize;
  DWORD          dwParams;
  DWORD          dwExecutor;
  int            TimeZoneOffsetMinutes;
  int            DaylightSavingOffsetMinutes;
  RILSYSTEMTIME  SysTime;
  DWORD          dwSystemTypes;
} RILNITZINFO_V2, RILNITZINFO_V2;
````

## Members

        
            `cbSize`

            
        
            `DaylightSavingOffsetMinutes`

            
        
            `dwExecutor`

            
        
            `dwParams`

            
        
            `dwSystemTypes`

            
        
            `SysTime`

            
        
            `TimeZoneOffsetMinutes`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |