---
UID: NS:ntddrilapitypes.RILEMERGENCYNUMBERSLIST
title: RILEMERGENCYNUMBERSLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumberslist.htm
old-project: netvista
ms.assetid: bfeaff04-6dd2-4889-9ab3-f20361dc2f5c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILEMERGENCYNUMBERSLIST, *LPRILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST
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
req.alt-api: RILEMERGENCYNUMBERSLIST
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
req.typenames: *LPRILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST
---

# RILEMERGENCYNUMBERSLIST structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILEMERGENCYNUMBERSLIST {
  DWORD                  cbSize;
  DWORD                  dwRilENSize;
  RILEMERGENCYNUMBER [1] RilEN;
} RILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST;
````


## -struct-fields

### -field cbSize


### -field dwRilENSize


### -field RilEN


## -remarks
