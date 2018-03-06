---
UID: NS:rilapitypes.RILUICCAPPINFO
title: RILUICCAPPINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappinfo_2.htm
old-project: netvista
ms.assetid: 7673163e-3663-4dc0-b454-bf358b87d62d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILUICCAPPINFO, RILUICCAPPINFO, RILUICCAPPINFO structure [Network Drivers Starting with Windows Vista], netvista.riluiccappinfo_2, rilapitypes/RILUICCAPPINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCAPPINFO
product: Windows
targetos: Windows
req.typenames: RILUICCAPPINFO, *LPRILUICCAPPINFO
req.product: Windows 10 or later.
---

# RILUICCAPPINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCAPPINFO {
  DWORD                    cbSize;
  DWORD                    dwParams;
  HUICCAPP                 hUiccApp;
  RILUICCAPPTYPE           dwUiccAppType;
  DWORD                    dwAppIdLength;
  BYTE [MAXLENGTH_APPID]   bAppId;
  DWORD                    dwAppNameLength;
  char [MAXLENGTH_APPNAME] cszAppName;
  DWORD                    dwNumPins;
  BYTE [MAXNUM_PINREF]     bPinRef;
} RILUICCAPPINFO, RILUICCAPPINFO;
````

## Members


`bAppId`



`bPinRef`



`cbSize`



`cszAppName`



`dwAppIdLength`



`dwAppNameLength`



`dwNumPins`



`dwParams`



`dwUiccAppType`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |