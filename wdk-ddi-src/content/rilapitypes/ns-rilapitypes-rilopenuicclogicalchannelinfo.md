---
UID: NS:rilapitypes.RILOPENUICCLOGICALCHANNELINFO
title: RILOPENUICCLOGICALCHANNELINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelinfo_2.htm
old-project: netvista
ms.assetid: f731c790-4348-4c18-aef1-184c3d4bf258
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO structure [Network Drivers Starting with Windows Vista], netvista.rilopenuicclogicalchannelinfo_2, rilapitypes/RILOPENUICCLOGICALCHANNELINFO"
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
-	RILOPENUICCLOGICALCHANNELINFO
product: Windows
targetos: Windows
req.typenames: RILOPENUICCLOGICALCHANNELINFO, *LPRILOPENUICCLOGICALCHANNELINFO
req.product: Windows 10 or later.
---

# RILOPENUICCLOGICALCHANNELINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILOPENUICCLOGICALCHANNELINFO {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwChannelId;
  DWORD    dwSelectResponseLength;
  BYTE [1] bSelectResponse;
} RILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO;
````

## Members


`bSelectResponse`



`cbSize`



`dwChannelId`



`dwParams`



`dwSelectResponseLength`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |