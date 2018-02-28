---
UID: NS:rilapitypes.RILEMERGENCYNUMBERSLIST
title: RILEMERGENCYNUMBERSLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumberslist_2.htm
old-project: netvista
ms.assetid: 06816431-a6fc-4c24-a31d-c486a4ba667f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST structure [Network Drivers Starting with Windows Vista], netvista.rilemergencynumberslist_2, rilapitypes/RILEMERGENCYNUMBERSLIST"
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
| **Header** | rilapitypes.h |