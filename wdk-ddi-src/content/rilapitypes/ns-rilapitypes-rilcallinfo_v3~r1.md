---
UID: NS.RILAPITYPES.RILCALLINFO_V3~R1
title: RILCALLINFO_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v3_2.htm
old-project: netvista
ms.assetid: 70224c7f-ec63-4d31-b66a-c41208a1b7ba
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLINFO_V3, *LPRILCALLINFO_V3, RILCALLINFO_V3
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
req.alt-api: RILCALLINFO_V3
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

# RILCALLINFO_V3 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILCALLINFO_V3 {
  DWORD                           cbSize;
  DWORD                           dwParams;
  DWORD                           dwExecutor;
  DWORD                           dwID;
  RILCALLINFODIRECTION            dwDirection;
  RILCALLINFOSTATUS               dwStatus;
  RILCALLTYPE                     dwType;
  RILCALLINFOMULTIPARTY           dwMultiparty;
  RILADDRESS                      raAddress;
  RILSUBADDRESS                   rsaSubAddress;
  WCHAR [MAXLENGTH_DESCRIPTION]   wszDescription;
  RILREMOTEPARTYINFOVALUE         dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE         dwNamePresentationIndicator;
  DWORD                           dwFlags;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
  RILCALLMEDIAOFFERANSWERSET      rcmOfferAnswer;
  RILCALLHANDOVERSTATE            rchsHandoverState;
} RILCALLINFO_V3, RILCALLINFO_V3;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field dwDirection


### -field dwStatus


### -field dwType


### -field dwMultiparty


### -field raAddress


### -field rsaSubAddress


### -field wszDescription


### -field dwNumberPresentationIndicator


### -field dwNamePresentationIndicator


### -field dwFlags


### -field dwDisconnectInitiator


### -field dwDisconnectReason


### -field stDisconnectDetails


### -field rcmOfferAnswer


### -field rchsHandoverState


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