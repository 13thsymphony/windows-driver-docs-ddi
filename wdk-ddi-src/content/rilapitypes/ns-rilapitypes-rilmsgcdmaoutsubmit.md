---
UID : NS:rilapitypes.RILMSGCDMAOUTSUBMIT
title : RILMSGCDMAOUTSUBMIT
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgcdmaoutsubmit_2.htm
old-project : netvista
ms.assetid : f74fe6cb-f38c-49ab-957f-9b3d163059c6
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT, *LPRILMSGCDMAOUTSUBMIT
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
req.alt-api : RILMSGCDMAOUTSUBMIT
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
req.typenames : RILMSGCDMAOUTSUBMIT, *LPRILMSGCDMAOUTSUBMIT
req.product : Windows 10 or later.
---

# RILMSGCDMAOUTSUBMIT structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGCDMAOUTSUBMIT {
  RILADDRESS                raDestAddress;
  RILSUBADDRESS             rsaDestSubaddr;
  BOOL                      bDigit;
  RILSYSTEMTIME             stValidityPeriodAbs;
  RILSYSTEMTIME             stValidityPeriodRel;
  RILSYSTEMTIME             stDeferredDelTimeAbs;
  RILSYSTEMTIME             stDeferredDelTimeRel;
  BOOL                      bDeliveryAckRequest;
  BOOL                      bUserAckRequest;
  BOOL                      bBearerReplyRequest;
  DWORD                     dwReplySeqNumber;
  RILMSGCDMAMSGDISPLAYMODE  dwMsgDisplayMode;
  RILADDRESS                raCallBackNumber;
  RILMSGCDMAMSGPRIORITY     dwMsgPriority;
  RILMSGCDMAMSGPRIVACY      dwMsgPrivacy;
  DWORD                     dwTeleservice;
  DWORD                     dwMsgID;
  RILMSGCDMALANGUAGE        dwMsgLang;
  RILMSGCDMAMSGENCODING     dwMsgEncoding;
  DWORD                     cbHdrLength;
  DWORD                     cchMsgLength;
  BYTE [MAXLENGTH_CDMAHDR]  rgbHdr;
  BYTE [MAXLENGTH_CDMAMSG]  rgbMsg;
} RILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT;
````

## Members

        
            `bBearerReplyRequest`

            
        
            `bDeliveryAckRequest`

            
        
            `bDigit`

            
        
            `bUserAckRequest`

            
        
            `cbHdrLength`

            
        
            `cchMsgLength`

            
        
            `dwMsgDisplayMode`

            
        
            `dwMsgEncoding`

            
        
            `dwMsgID`

            
        
            `dwMsgLang`

            
        
            `dwMsgPriority`

            
        
            `dwMsgPrivacy`

            
        
            `dwReplySeqNumber`

            
        
            `dwTeleservice`

            
        
            `raCallBackNumber`

            
        
            `raDestAddress`

            
        
            `rgbHdr`

            
        
            `rgbMsg`

            
        
            `rsaDestSubaddr`

            
        
            `stDeferredDelTimeAbs`

            
        
            `stDeferredDelTimeRel`

            
        
            `stValidityPeriodAbs`

            
        
            `stValidityPeriodRel`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |