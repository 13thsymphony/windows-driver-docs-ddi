---
UID : NS:rilapitypes.RILADDITIONALCALLERINFO
title : RILADDITIONALCALLERINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riladditionalcallerinfo_2.htm
old-project : netvista
ms.assetid : e29f6710-0ca1-4420-b0e7-957ba020254b
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILADDITIONALCALLERINFO, *LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO
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
req.alt-api : RILADDITIONALCALLERINFO
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
req.typenames : "*LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO"
req.product : Windows 10 or later.
---

# RILADDITIONALCALLERINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILADDITIONALCALLERINFO {
  DWORD     cbSize;
  DWORD     dwParams;
  DWORD     dwExecutor;
  DWORD     dwCallId;
  DWORD     dwCallerInfoLength;
  WCHAR [1] wszCallerInfo;
} RILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO;
````

## Members

        
            `cbSize`

            
        
            `dwCallerInfoLength`

            
        
            `dwCallId`

            
        
            `dwExecutor`

            
        
            `dwParams`

            
        
            `wszCallerInfo`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |