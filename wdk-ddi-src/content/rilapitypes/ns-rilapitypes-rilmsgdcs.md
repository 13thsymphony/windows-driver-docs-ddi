---
UID: NS:rilapitypes.RILMSGDCS
title: RILMSGDCS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcs.htm
old-project: netvista
ms.assetid: b9d37683-fd3d-42fd-9ec2-128b76325868
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMSGDCS, RILMSGDCS, RILMSGDCS structure [Network Drivers Starting with Windows Vista], netvista.rilmsgdcs, ntddrilapitypes/RILMSGDCS"
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
-	RILMSGDCS
product: Windows
targetos: Windows
req.typenames: RILMSGDCS, *LPRILMSGDCS
req.product: Windows 10 or later.
---

# RILMSGDCS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGDCS {
  DWORD                cbSize;
  DWORD                dwParams;
  RILMSGDCSTYPE        dwType;
  DWORD                dwFlags;
  RILMSGDCSMSGCLASS    dwMsgClass;
  RILMSGDCSALPHABET    dwAlphabet;
  RILMSGDCSINDICATION  dwIndication;
  DWORD                dwLanguage;
} RILMSGDCS, RILMSGDCS;
````

## Members


`cbSize`



`dwAlphabet`



`dwFlags`



`dwIndication`



`dwLanguage`



`dwMsgClass`



`dwParams`



`dwType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |