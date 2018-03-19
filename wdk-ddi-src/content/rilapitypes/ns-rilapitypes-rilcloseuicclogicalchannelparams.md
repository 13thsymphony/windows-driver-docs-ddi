---
UID: NS:rilapitypes.RILCLOSEUICCLOGICALCHANNELPARAMS
title: RILCLOSEUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcloseuicclogicalchannelparams.htm
old-project: netvista
ms.assetid: 0c06bcd7-d475-40b8-b997-fe65047db331
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilcloseuicclogicalchannelparams, ntddrilapitypes/RILCLOSEUICCLOGICALCHANNELPARAMS"
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
-	RILCLOSEUICCLOGICALCHANNELPARAMS
product: Windows
targetos: Windows
req.typenames: RILCLOSEUICCLOGICALCHANNELPARAMS, *LPRILCLOSEUICCLOGICALCHANNELPARAMS
req.product: Windows 10 or later.
---

# RILCLOSEUICCLOGICALCHANNELPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCLOSEUICCLOGICALCHANNELPARAMS {
  DWORD  dwSlotIndex;
  DWORD  dwChannelId;
} RILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS;
````

## Members


`dwSlotIndex`



`dwChannelId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |