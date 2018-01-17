---
UID: NS:ntddrilapitypes.RILTONESIGNALINFO_V1
title: RILTONESIGNALINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v1.htm
old-project: netvista
ms.assetid: 3434112f-54b4-4494-8514-fd3d8dc33329
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILTONESIGNALINFO_V1, *LPRILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1
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
req.alt-api: RILTONESIGNALINFO_V1
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
req.typenames: *LPRILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1
---

# RILTONESIGNALINFO_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILTONESIGNALINFO_V1 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwGPPTone


### -field dwGPP2Tone


### -field dwGPP2IsdnAlerting


## -remarks
