---
UID: NS.RILAPITYPES.RILMSGCDMAOUTSUBMIT
title: RILMSGCDMAOUTSUBMIT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmaoutsubmit_2.htm
old-project: NetVista
ms.assetid: f74fe6cb-f38c-49ab-957f-9b3d163059c6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILMSGCDMAOUTSUBMIT, *LPRILMSGCDMAOUTSUBMIT, RILMSGCDMAOUTSUBMIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMSGCDMAOUTSUBMIT
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
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
  BYTE [MAXLENGTH_CDMAHDR]  rgbHdr;
  BYTE [MAXLENGTH_CDMAMSG]  rgbMsg;
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


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>