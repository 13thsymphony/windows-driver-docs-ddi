---
UID: NS:ntddrilapitypes.RILMESSAGEINUICC
title: RILMESSAGEINUICC
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinuicc.htm
old-project: netvista
ms.assetid: 71f48863-06dd-4ea1-a8b7-fdf673090fe0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMESSAGEINUICC, RILMESSAGEINUICC, RILMESSAGEINUICC structure [Network Drivers Starting with Windows Vista], netvista.rilmessageinuicc, ntddrilapitypes/RILMESSAGEINUICC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILMESSAGEINUICC
product: Windows
targetos: Windows
req.typenames: RILMESSAGEINUICC, *LPRILMESSAGEINUICC
---

# RILMESSAGEINUICC structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMESSAGEINUICC {
  DWORD     cbSize;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILMESSAGEINUICC, RILMESSAGEINUICC;
````

## Members


`cbSize`



`dwExecutor`



`dwIndex`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |