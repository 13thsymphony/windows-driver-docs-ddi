---
UID: NS:ntddrilapitypes.RILUICCSERVICEINFO
title: RILUICCSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccserviceinfo.htm
old-project: netvista
ms.assetid: 80abf9a7-0a34-4fc2-ab5a-afcb678b7003
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILUICCSERVICEINFO, *LPRILUICCSERVICEINFO, netvista.riluiccserviceinfo, RILUICCSERVICEINFO, RILUICCSERVICEINFO structure [Network Drivers Starting with Windows Vista]
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
-	RILUICCSERVICEINFO
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICEINFO, *LPRILUICCSERVICEINFO
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
| **Header** | ntddrilapitypes.h |