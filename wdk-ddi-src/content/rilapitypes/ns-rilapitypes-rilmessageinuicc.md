---
UID: NS:rilapitypes.RILMESSAGEINUICC
title: RILMESSAGEINUICC
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinuicc_2.htm
old-project: netvista
ms.assetid: 2a956b25-1cf5-4a51-bc60-c4a7a7f70e2c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILMESSAGEINUICC, rilapitypes/RILMESSAGEINUICC, RILMESSAGEINUICC structure [Network Drivers Starting with Windows Vista], netvista.rilmessageinuicc_2, *LPRILMESSAGEINUICC
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
-	RILMESSAGEINUICC
product: Windows
targetos: Windows
req.typenames: RILMESSAGEINUICC, *LPRILMESSAGEINUICC
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |