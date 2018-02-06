---
UID: NS:rilapitypes.RILCALLINFO_V3
title: RILCALLINFO_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v3_2.htm
old-project: netvista
ms.assetid: 70224c7f-ec63-4d31-b66a-c41208a1b7ba
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallinfo_v3_2, RILCALLINFO_V3 structure [Network Drivers Starting with Windows Vista], RILCALLINFO_V3, rilapitypes/RILCALLINFO_V3, *LPRILCALLINFO_V3
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLINFO_V3
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLINFO_V3, RILCALLINFO_V3"
req.product: Windows 10 or later.
---

# RILCALLINFO_V3 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
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

## Members


`cbSize`



`dwDirection`



`dwDisconnectInitiator`



`dwDisconnectReason`



`dwExecutor`



`dwFlags`



`dwID`



`dwMultiparty`



`dwNamePresentationIndicator`



`dwNumberPresentationIndicator`



`dwParams`



`dwStatus`



`dwType`



`raAddress`



`rchsHandoverState`



`rcmOfferAnswer`



`rsaSubAddress`



`stDisconnectDetails`



`wszDescription`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |