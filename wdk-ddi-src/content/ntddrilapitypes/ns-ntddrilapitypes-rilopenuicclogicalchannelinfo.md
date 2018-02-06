---
UID: NS:ntddrilapitypes.RILOPENUICCLOGICALCHANNELINFO
title: RILOPENUICCLOGICALCHANNELINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelinfo.htm
old-project: netvista
ms.assetid: 5001f623-5b53-4ae7-9b5b-dc3bd5bdcc70
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilopenuicclogicalchannelinfo, RILOPENUICCLOGICALCHANNELINFO structure [Network Drivers Starting with Windows Vista], RILOPENUICCLOGICALCHANNELINFO, *LPRILOPENUICCLOGICALCHANNELINFO, ntddrilapitypes/RILOPENUICCLOGICALCHANNELINFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILOPENUICCLOGICALCHANNELINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO"
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
| **Header** | ntddrilapitypes.h |