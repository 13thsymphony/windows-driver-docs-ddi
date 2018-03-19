---
UID: NS:rilapitypes.RILTONESIGNALINFO_V1
title: RILTONESIGNALINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v1.htm
old-project: netvista
ms.assetid: 3434112f-54b4-4494-8514-fd3d8dc33329
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.riltonesignalinfo_v1, ntddrilapitypes/RILTONESIGNALINFO_V1"
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
-	RILTONESIGNALINFO_V1
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFO_V1, *LPRILTONESIGNALINFO_V1
req.product: Windows 10 or later.
---

# RILTONESIGNALINFO_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILTONESIGNALINFO_V1 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1;
````

## Members


`cbSize`



`dwParams`



`dwGPPTone`



`dwGPP2Tone`



`dwGPP2IsdnAlerting`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |