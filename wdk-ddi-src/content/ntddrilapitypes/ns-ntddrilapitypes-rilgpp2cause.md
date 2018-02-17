---
UID: NS:ntddrilapitypes.RILGPP2CAUSE
title: RILGPP2CAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgpp2cause.htm
old-project: netvista
ms.assetid: 40981ad1-9a3e-47c5-a3d2-e980659b8ca4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILGPP2CAUSE, RILGPP2CAUSE structure [Network Drivers Starting with Windows Vista], *LPRILGPP2CAUSE, netvista.rilgpp2cause, RILGPP2CAUSE
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
-	RILGPP2CAUSE
product: Windows
targetos: Windows
req.typenames: RILGPP2CAUSE, *LPRILGPP2CAUSE
---

# RILGPP2CAUSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGPP2CAUSE {
  DWORD  dwCauseValue;
} RILGPP2CAUSE, RILGPP2CAUSE;
````

## Members


`dwCauseValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |