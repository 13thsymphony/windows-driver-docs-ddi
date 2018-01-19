---
UID : NS:rilapitypes.RILCALLRTT
title : RILCALLRTT
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallrtt_2.htm
old-project : netvista
ms.assetid : e11103c6-665f-4673-8c53-5b35abf0299d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILCALLRTT, *LPRILCALLRTT, RILCALLRTT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RILCALLRTT
req.alt-loc : rilapitypes.h
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
req.typenames : "*LPRILCALLRTT, RILCALLRTT"
req.product : Windows 10 or later.
---

# RILCALLRTT structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLRTT {
  RILCALLRTTACTION  dwRTTAction;
  RILCALLRTTMODE    dwRTTModeType;
  RILCALLRTTCAP     stRTTCap;
} RILCALLRTT, RILCALLRTT;
````

## Members

        
            `dwRTTAction`

            
        
            `dwRTTModeType`

            
        
            `stRTTCap`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |