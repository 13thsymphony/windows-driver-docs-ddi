---
UID: NS:ntddrilapitypes.RILMSGCDMAOUTSUBMIT
title: RILMSGCDMAOUTSUBMIT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmaoutsubmit.htm
old-project: netvista
ms.assetid: 3ed93cff-7974-4cf9-9b89-f4a8e52c4c3d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGCDMAOUTSUBMIT, *LPRILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMSGCDMAOUTSUBMIT
req.alt-loc: ntddrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *LPRILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT
---

# RILMSGCDMAOUTSUBMIT structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

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
  BYTE [140]                rgbHdr;
  BYTE [256]                rgbMsg;
} RILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT;
````


## -struct-fields

### -field raDestAddress


### -field rsaDestSubaddr


### -field bDigit


### -field stValidityPeriodAbs


### -field stValidityPeriodRel


### -field stDeferredDelTimeAbs


### -field stDeferredDelTimeRel


### -field bDeliveryAckRequest


### -field bUserAckRequest


### -field bBearerReplyRequest


### -field dwReplySeqNumber


### -field dwMsgDisplayMode


### -field raCallBackNumber


### -field dwMsgPriority


### -field dwMsgPrivacy


### -field dwTeleservice


### -field dwMsgID


### -field dwMsgLang


### -field dwMsgEncoding


### -field cbHdrLength


### -field cchMsgLength


### -field rgbHdr


### -field rgbMsg


## -remarks
