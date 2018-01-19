---
UID : NS:rilapitypes.RILMSGBCGENERAL
title : RILMSGBCGENERAL
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgbcgeneral_2.htm
old-project : netvista
ms.assetid : 7202683f-5e02-48dd-b8b7-cb998fd660df
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILMSGBCGENERAL, *LPRILMSGBCGENERAL, RILMSGBCGENERAL
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
req.alt-api : RILMSGBCGENERAL
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
req.typenames : "*LPRILMSGBCGENERAL, RILMSGBCGENERAL"
req.product : Windows 10 or later.
---

# RILMSGBCGENERAL structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGBCGENERAL {
  RILGEOSCOPE                       dwGeoScope;
  DWORD                             dwMsgCode;
  DWORD                             dwUpdateNumber;
  DWORD                             dwID;
  DWORD                             dwSerialNumber;
  RILMSGDCS                         rmdDataCoding;
  DWORD                             dwTotalPages;
  DWORD                             dwPageNumber;
  RILMSGBCGENERALWARNINGTYPE        dwWarningType;
  BOOL                              bEmergencyUserAlert;
  BOOL                              bMessagePopup;
  RILSYSTEMTIME                     stSCReceiveTime;
  BYTE [MAXLENGTH_DIGITALSIGNATURE] digSig;
  DWORD                             cchMsgLength;
  BYTE [MAXLENGTH_MSG]              rgbMsg;
} RILMSGBCGENERAL, RILMSGBCGENERAL;
````

## Members

        
            `bEmergencyUserAlert`

            
        
            `bMessagePopup`

            
        
            `cchMsgLength`

            
        
            `digSig`

            
        
            `dwGeoScope`

            
        
            `dwID`

            
        
            `dwMsgCode`

            
        
            `dwPageNumber`

            
        
            `dwSerialNumber`

            
        
            `dwTotalPages`

            
        
            `dwUpdateNumber`

            
        
            `dwWarningType`

            
        
            `rgbMsg`

            
        
            `rmdDataCoding`

            
        
            `stSCReceiveTime`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |