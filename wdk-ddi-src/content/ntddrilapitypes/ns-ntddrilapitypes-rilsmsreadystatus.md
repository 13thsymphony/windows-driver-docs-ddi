---
UID: NS:ntddrilapitypes.RILSMSREADYSTATUS
title: RILSMSREADYSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystatus.htm
old-project: netvista
ms.assetid: 0f2d6a06-18af-4e7a-9f88-c81d98575f56
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSMSREADYSTATUS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILSMSREADYSTATUS, RILSMSREADYSTATUS, netvista.rilsmsreadystatus, *LPRILSMSREADYSTATUS
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
-	RILSMSREADYSTATUS
product: Windows
targetos: Windows
req.typenames: RILSMSREADYSTATUS, *LPRILSMSREADYSTATUS
---

# RILSMSREADYSTATUS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSMSREADYSTATUS {
  DWORD             cbSize;
  DWORD             dwParams;
  DWORD             dwExecutor;
  RILSMSREADYSTATE  dwReadyState;
} RILSMSREADYSTATUS, RILSMSREADYSTATUS;
````

## Members


`cbSize`



`dwExecutor`



`dwParams`



`dwReadyState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |