---
UID: NS:rilapitypes.RILUICCFILES
title: RILUICCFILES
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfiles.htm
old-project: netvista
ms.assetid: a29f2ff6-1c15-4313-b3a5-73fb8d40d2d7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILUICCFILES, RILUICCFILES, RILUICCFILES structure [Network Drivers Starting with Windows Vista], netvista.riluiccfiles, ntddrilapitypes/RILUICCFILES"
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
-	RILUICCFILES
product: Windows
targetos: Windows
req.typenames: RILUICCFILES, *LPRILUICCFILES
req.product: Windows 10 or later.
---

# RILUICCFILES structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCFILES {
  DWORD               cbSize;
  DWORD               dwNumFiles;
  RILUICCFILEPATH [1] filePath;
} RILUICCFILES, RILUICCFILES;
````

## Members


`cbSize`



`dwNumFiles`



`filePath`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |