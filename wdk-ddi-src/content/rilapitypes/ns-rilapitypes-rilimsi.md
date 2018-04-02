---
UID: NS:rilapitypes.RILIMSI
title: RILIMSI
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsi_2.htm
old-project: netvista
ms.assetid: 0ec6eead-debb-4901-a099-6ecef19bc4c9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILIMSI, RILIMSI, RILIMSI structure [Network Drivers Starting with Windows Vista], netvista.rilimsi_2, rilapitypes/RILIMSI"
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
-	RILIMSI
product:
- Windows
targetos: Windows
req.typenames: RILIMSI, *LPRILIMSI
req.product: Windows 10 or later.
---

# RILIMSI structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILIMSI {
  DWORD                  cbSize;
  DWORD                  dwParams;
  WCHAR [MAXLENGTH_IMSI] wszImsi;
  DWORD                  dwMcc;
  DWORD                  dwMnc;
} RILIMSI, RILIMSI;
````

## Members


`cbSize`



`dwParams`



`wszImsi`



`dwMcc`



`dwMnc`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |