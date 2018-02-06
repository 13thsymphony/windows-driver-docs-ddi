---
UID: NS:ntddrilapitypes.RILUICCFILEPATH
title: RILUICCFILEPATH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilepath.htm
old-project: netvista
ms.assetid: 65c46391-f0ef-4618-ac26-86f41e04e688
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCFILEPATH structure [Network Drivers Starting with Windows Vista], RILUICCFILEPATH, netvista.riluiccfilepath, *LPRILUICCFILEPATH, ntddrilapitypes/RILUICCFILEPATH
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
-	RILUICCFILEPATH
product: Windows
targetos: Windows
req.typenames: RILUICCFILEPATH, *LPRILUICCFILEPATH
---

# RILUICCFILEPATH structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCFILEPATH {
  HUICCAPP  hUiccApp;
  DWORD     dwFilePathLen;
  WORD [8]  wFilePath;
} RILUICCFILEPATH, RILUICCFILEPATH;
````

## Members


`dwFilePathLen`



`hUiccApp`



`wFilePath`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |