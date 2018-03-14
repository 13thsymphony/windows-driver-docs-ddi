---
UID: NS:rilapitypes.RILEMERGENCYNUMBERSLIST
title: RILEMERGENCYNUMBERSLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumberslist.htm
old-project: netvista
ms.assetid: bfeaff04-6dd2-4889-9ab3-f20361dc2f5c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST structure [Network Drivers Starting with Windows Vista], netvista.rilemergencynumberslist, ntddrilapitypes/RILEMERGENCYNUMBERSLIST"
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
-	RILEMERGENCYNUMBERSLIST
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYNUMBERSLIST, *LPRILEMERGENCYNUMBERSLIST
req.product: Windows 10 or later.
---

# RILEMERGENCYNUMBERSLIST structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEMERGENCYNUMBERSLIST {
  DWORD                  cbSize;
  DWORD                  dwRilENSize;
  RILEMERGENCYNUMBER [1] RilEN;
} RILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST;
````

## Members


`cbSize`



`dwRilENSize`



`RilEN`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |