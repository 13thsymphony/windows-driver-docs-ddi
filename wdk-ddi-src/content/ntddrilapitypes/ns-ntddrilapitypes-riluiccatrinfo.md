---
UID: NS:ntddrilapitypes.RILUICCATRINFO
title: RILUICCATRINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccatrinfo.htm
old-project: netvista
ms.assetid: 84ced2d3-43a9-42ef-b8fb-592dc960b01b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCATRINFO, netvista.riluiccatrinfo, ntddrilapitypes/RILUICCATRINFO, *LPRILUICCATRINFO, RILUICCATRINFO structure [Network Drivers Starting with Windows Vista]
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
-	RILUICCATRINFO
product: Windows
targetos: Windows
req.typenames: RILUICCATRINFO, *LPRILUICCATRINFO
---

# RILUICCATRINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCATRINFO {
  DWORD     dwATRlength;
  BYTE [36] bATR;
} RILUICCATRINFO, RILUICCATRINFO;
````

## Members


`bATR`



`dwATRlength`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |