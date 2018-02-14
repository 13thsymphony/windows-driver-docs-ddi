---
UID: NS:ntddrilapitypes.RILCALLLIST_V2
title: RILCALLLIST_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v2.htm
old-project: netvista
ms.assetid: 4cf94a04-dbb4-4e24-954b-3a5a720ef963
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLLIST_V2 structure [Network Drivers Starting with Windows Vista], *LPRILCALLLIST_V2, RILCALLLIST_V2, netvista.rilcalllist_v2, ntddrilapitypes/RILCALLLIST_V2
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
-	RILCALLLIST_V2
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLLIST_V2, RILCALLLIST_V2"
---

# RILCALLLIST_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLLIST_V2 {
  DWORD              dwNumberOfCalls;
  RILCALLINFO_V2 [1] rciCallInfo;
} RILCALLLIST_V2, RILCALLLIST_V2;
````

## Members


`dwNumberOfCalls`



`rciCallInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |