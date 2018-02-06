---
UID: NS:rilapitypes.RILDISPLAYINFO
title: RILDISPLAYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfo_2.htm
old-project: netvista
ms.assetid: f24d8122-ea07-477f-9cf9-4767cc0fbf86
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILDISPLAYINFO, *LPRILDISPLAYINFO, RILDISPLAYINFO, RILDISPLAYINFO structure [Network Drivers Starting with Windows Vista], netvista.rildisplayinfo_2
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
-	RILDISPLAYINFO
product: Windows
targetos: Windows
req.typenames: RILDISPLAYINFO, *LPRILDISPLAYINFO
req.product: Windows 10 or later.
---

# RILDISPLAYINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILDISPLAYINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  RILDISPLAYINFOTYPE  dwType;
  RILDISPLAYINFOTAG   dwTag;
  DWORD               dwMessageSize;
  BYTE [1]            pbMessage;
} RILDISPLAYINFO, RILDISPLAYINFO;
````

## Members


`cbSize`



`dwExecutor`



`dwMessageSize`



`dwParams`



`dwTag`



`dwType`



`pbMessage`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |