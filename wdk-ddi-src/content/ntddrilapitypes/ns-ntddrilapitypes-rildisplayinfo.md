---
UID: NS:ntddrilapitypes.RILDISPLAYINFO
title: RILDISPLAYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfo.htm
old-project: netvista
ms.assetid: 6c28e50c-a76a-4a7c-af29-6e58bcfe3f3b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILDISPLAYINFO, netvista.rildisplayinfo, RILDISPLAYINFO, RILDISPLAYINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILDISPLAYINFO"
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
-	RILDISPLAYINFO
product: Windows
targetos: Windows
req.typenames: RILDISPLAYINFO, *LPRILDISPLAYINFO
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
| **Header** | ntddrilapitypes.h |