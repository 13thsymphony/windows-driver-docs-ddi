---
UID: NS:ntddrilapitypes.RILOPENUICCLOGICALCHANNELPARAMS
title: RILOPENUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelparams.htm
old-project: netvista
ms.assetid: 4bc3a16b-dc9e-4c15-9083-75ac4608def5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilopenuicclogicalchannelparams, ntddrilapitypes/RILOPENUICCLOGICALCHANNELPARAMS"
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
-	RILOPENUICCLOGICALCHANNELPARAMS
product: Windows
targetos: Windows
req.typenames: RILOPENUICCLOGICALCHANNELPARAMS, *LPRILOPENUICCLOGICALCHANNELPARAMS
---

# RILOPENUICCLOGICALCHANNELPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILOPENUICCLOGICALCHANNELPARAMS {
  DWORD     dwSlotIndex;
  DWORD     dwChannelGroup;
  DWORD     dwAppIdLength;
  BYTE [32] bAppId;
  DWORD     dwSelectP2Arg;
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
| **Header** | ntddrilapitypes.h |