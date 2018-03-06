---
UID: NS:ntddrilapitypes.RILCALLAUDIOMEDIASTATE
title: RILCALLAUDIOMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastate.htm
old-project: netvista
ms.assetid: f8e65085-6837-4d49-a39e-784942ee39a4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallaudiomediastate, ntddrilapitypes/RILCALLAUDIOMEDIASTATE"
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
-	RILCALLAUDIOMEDIASTATE
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOMEDIASTATE, *LPRILCALLAUDIOMEDIASTATE
---

# RILCALLAUDIOMEDIASTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLAUDIOMEDIASTATE {
  DWORD                dwParams;
  RILCALLAUDIOSOURCE   dwAudioSource;
  RILCALLAUDIOQUALITY  dwAudioQuality;
  DWORD                dwFlags;
} RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE;
````

## Members


`dwAudioQuality`



`dwAudioSource`



`dwFlags`



`dwParams`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |