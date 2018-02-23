---
UID: NS:rilapitypes.RILOPENUICCLOGICALCHANNELPARAMS
title: RILOPENUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelparams_2.htm
old-project: netvista
ms.assetid: 067d33bf-33d5-49b7-9923-8c893d0b9184
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILOPENUICCLOGICALCHANNELPARAMS, netvista.rilopenuicclogicalchannelparams_2, *LPRILOPENUICCLOGICALCHANNELPARAMS, rilapitypes/RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS structure [Network Drivers Starting with Windows Vista]
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
-	RILOPENUICCLOGICALCHANNELPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS"
req.product: Windows 10 or later.
---

# RILOPENUICCLOGICALCHANNELPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILOPENUICCLOGICALCHANNELPARAMS {
  DWORD                  dwSlotIndex;
  DWORD                  dwChannelGroup;
  DWORD                  dwAppIdLength;
  BYTE [MAXLENGTH_APPID] bAppId;
  DWORD                  dwSelectP2Arg;
} RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS;
````

## Members


`bAppId`



`dwAppIdLength`



`dwChannelGroup`



`dwSelectP2Arg`



`dwSlotIndex`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |