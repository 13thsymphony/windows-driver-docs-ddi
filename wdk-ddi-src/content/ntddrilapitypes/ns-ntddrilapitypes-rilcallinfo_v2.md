---
UID : NS:ntddrilapitypes.RILCALLINFO_V2
title : RILCALLINFO_V2
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallinfo_v2.htm
old-project : netvista
ms.assetid : 02eaaaa4-fe88-4f07-bfbf-1ba52d0c1362
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILCALLINFO_V2, netvista.rilcallinfo_v2, RILCALLINFO_V2 structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILCALLINFO_V2, *LPRILCALLINFO_V2
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILCALLINFO_V2, RILCALLINFO_V2"
---

# RILCALLINFO_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLINFO_V2 {
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
  WCHAR [256]                     wszDescription;
  RILREMOTEPARTYINFOVALUE         dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE         dwNamePresentationIndicator;
  DWORD                           dwFlags;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
} RILCALLINFO_V2, RILCALLINFO_V2;
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



`rsaSubAddress`



`stDisconnectDetails`



`wszDescription`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |