---
UID: NS:ntddrilapitypes.RILMSGCDMAINDELIVER
title: RILMSGCDMAINDELIVER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmaindeliver.htm
old-project: netvista
ms.assetid: fdff17ac-2ffd-45b0-8f01-a21af1ffa9d0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILMSGCDMAINDELIVER, *LPRILMSGCDMAINDELIVER, RILMSGCDMAINDELIVER
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
req.alt-api: RILMSGCDMAINDELIVER
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
req.typenames: *LPRILMSGCDMAINDELIVER, RILMSGCDMAINDELIVER
---

# RILMSGCDMAINDELIVER structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMSGCDMAINDELIVER {
  RILADDRESS                raOrigAddress;
  RILSUBADDRESS             rsaOrigSubaddr;
  RILSYSTEMTIME             stSCReceiveTime;
  RILSYSTEMTIME             stValidityPeriodAbs;
  RILSYSTEMTIME             stValidityPeriodRel;
  RILSYSTEMTIME             stDeferredDelTimeAbs;
  RILSYSTEMTIME             stDeferredDelTimeRel;
  DWORD                     dwNumMsgs;
  RILADDRESS                raCallBackNumber;
  RILMSGCDMAMSGPRIORITY     dwMsgPriority;
  DWORD                     dwAlertOnMsgDelivery;
  RILMSGCDMAMSGPRIVACY      dwMsgPrivacy;
  BOOL                      bUserAckRequest;
  RILMSGCDMAMSGDISPLAYMODE  dwMsgDisplayMode;
  DWORD                     dwTeleservice;
  DWORD                     dwServiceID;
  DWORD                     dwMsgID;
  RILMSGCDMALANGUAGE        dwMsgLang;
  RILMSGCDMAMSGENCODING     dwMsgEncoding;
  DWORD                     cbHdrLength;
  DWORD                     cchMsgLength;
  BYTE [140]                rgbHdr;
  BYTE [256]                rgbMsg;
} RILMSGCDMAINDELIVER, RILMSGCDMAINDELIVER;
````


## -struct-fields

### -field raOrigAddress


### -field rsaOrigSubaddr


### -field stSCReceiveTime


### -field stValidityPeriodAbs


### -field stValidityPeriodRel


### -field stDeferredDelTimeAbs


### -field stDeferredDelTimeRel


### -field dwNumMsgs


### -field raCallBackNumber


### -field dwMsgPriority


### -field dwAlertOnMsgDelivery


### -field dwMsgPrivacy


### -field bUserAckRequest


### -field dwMsgDisplayMode


### -field dwTeleservice


### -field dwServiceID


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
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>