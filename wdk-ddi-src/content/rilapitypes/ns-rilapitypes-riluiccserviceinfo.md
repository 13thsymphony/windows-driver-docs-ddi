---
UID: NS:rilapitypes.RILUICCSERVICEINFO
title: RILUICCSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccserviceinfo_2.htm
old-project: netvista
ms.assetid: e96bc5b5-655f-49e3-8489-af79d427bc74
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCSERVICEINFO, *LPRILUICCSERVICEINFO, RILUICCSERVICEINFO structure [Network Drivers Starting with Windows Vista], netvista.riluiccserviceinfo_2, rilapitypes/RILUICCSERVICEINFO
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
-	RILUICCSERVICEINFO
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICEINFO, *LPRILUICCSERVICEINFO
req.product: Windows 10 or later.
---

# RILUICCSERVICEINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCSERVICEINFO {
  DWORD                  cbSize;
  RILUICCSERVICESERVICE  dwService;
  RILUICCSERVICESTATE    dwState;
} RILUICCSERVICEINFO, RILUICCSERVICEINFO;
````

## Members


`cbSize`



`dwService`



`dwState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |