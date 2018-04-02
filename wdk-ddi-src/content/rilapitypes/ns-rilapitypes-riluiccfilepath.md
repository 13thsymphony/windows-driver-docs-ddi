---
UID: NS:rilapitypes.RILUICCFILEPATH
title: RILUICCFILEPATH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilepath.htm
old-project: netvista
ms.assetid: 65c46391-f0ef-4618-ac26-86f41e04e688
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUICCFILEPATH, RILUICCFILEPATH, RILUICCFILEPATH structure [Network Drivers Starting with Windows Vista], netvista.riluiccfilepath, ntddrilapitypes/RILUICCFILEPATH"
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
-	RILUICCFILEPATH
product:
- Windows
targetos: Windows
req.typenames: RILUICCFILEPATH, *LPRILUICCFILEPATH
req.product: Windows 10 or later.
---

# RILUICCFILEPATH structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUICCFILEPATH {
  HUICCAPP hUiccApp;
  DWORD    dwFilePathLen;
  WORD     wFilePath[8];
}  *LPRILUICCFILEPATH;
```

## Members


`hUiccApp`



`dwFilePathLen`



`wFilePath`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |