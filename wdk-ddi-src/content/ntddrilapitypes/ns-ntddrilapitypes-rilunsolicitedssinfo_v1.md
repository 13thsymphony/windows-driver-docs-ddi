---
UID : NS:ntddrilapitypes.RILUNSOLICITEDSSINFO_V1
title : RILUNSOLICITEDSSINFO_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilunsolicitedssinfo_v1.htm
old-project : netvista
ms.assetid : c9681207-6cdd-40b6-8878-7ea37f383e4f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILUNSOLICITEDSSINFO_V1, *LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1
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
req.alt-api : RILUNSOLICITEDSSINFO_V1
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
req.typenames : "*LPRILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1"
---

# RILUNSOLICITEDSSINFO_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUNSOLICITEDSSINFO_V1 {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  DWORD                                 dwExecutor;
  DWORD                                 dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE  dwNotificationCode;
  RILADDRESS                            raAddress;
  RILSUBADDRESS                         rsaSubAddress;
  DWORD                                 dwCUGIndex;
} RILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1;
````

## Members

        
            `cbSize`

            
        
            `dwCUGIndex`

            
        
            `dwExecutor`

            
        
            `dwID`

            
        
            `dwNotificationCode`

            
        
            `dwParams`

            
        
            `raAddress`

            
        
            `rsaSubAddress`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |