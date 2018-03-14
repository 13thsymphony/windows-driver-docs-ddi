---
UID: NS:rilapitypes.RILTONESIGNALINFO_V2
title: RILTONESIGNALINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v2.htm
old-project: netvista
ms.assetid: e0c40d65-d290-4fae-9fa7-57a9bf047f13
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILTONESIGNALINFO, *LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO, RILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2 structure [Network Drivers Starting with Windows Vista], netvista.riltonesignalinfo_v2, ntddrilapitypes/RILTONESIGNALINFO_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	RILTONESIGNALINFO_V2
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFO_V2, *LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO, *LPRILTONESIGNALINFO
req.product: Windows 10 or later.
---

# RILTONESIGNALINFO_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILTONESIGNALINFO_V2 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  DWORD                 dwExecutor;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2;
````

## Members


`cbSize`



`dwExecutor`



`dwGPP2IsdnAlerting`



`dwGPP2Tone`



`dwGPPTone`



`dwParams`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |