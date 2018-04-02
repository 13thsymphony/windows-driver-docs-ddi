---
UID: NS:ntddrilapitypes.RILCALLINFO_V2
title: RILCALLINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v2.htm
old-project: netvista
ms.assetid: 02eaaaa4-fe88-4f07-bfbf-1ba52d0c1362
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLINFO_V2, RILCALLINFO_V2, RILCALLINFO_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilcallinfo_v2, ntddrilapitypes/RILCALLINFO_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCALLINFO_V2
product: Windows
targetos: Windows
req.typenames: RILCALLINFO_V2, *LPRILCALLINFO_V2
---

# RILCALLINFO_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLINFO_V2 {
  DWORD                          cbSize;
  DWORD                          dwParams;
  DWORD                          dwExecutor;
  DWORD                          dwID;
  RILCALLINFODIRECTION           dwDirection;
  RILCALLINFOSTATUS              dwStatus;
  RILCALLTYPE                    dwType;
  RILCALLINFOMULTIPARTY          dwMultiparty;
  RILADDRESS                     raAddress;
  RILSUBADDRESS                  rsaSubAddress;
  WCHAR                          wszDescription[256];
  RILREMOTEPARTYINFOVALUE        dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE        dwNamePresentationIndicator;
  DWORD                          dwFlags;
  RILCALLINFODISCONNECTINITIATOR dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON    dwDisconnectReason;
  RILCALLDISCONNECTDETAILS       stDisconnectDetails;
} *LPRILCALLINFO_V2, RILCALLINFO_V2;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwID`



`dwDirection`



`dwStatus`



`dwType`



`dwMultiparty`



`raAddress`



`rsaSubAddress`



`wszDescription`



`dwNumberPresentationIndicator`



`dwNamePresentationIndicator`



`dwFlags`



`dwDisconnectInitiator`



`dwDisconnectReason`



`stDisconnectDetails`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |