---
UID: NS:ntddrilapitypes.RILMESSAGEIN_V1
title: RILMESSAGEIN_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagein_v1.htm
old-project: netvista
ms.assetid: c9de99e4-556c-4b3b-a442-53fc52553d3d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMESSAGEIN_V1, RILMESSAGEIN_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilmessagein_v1, ntddrilapitypes/RILMESSAGEIN_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILMESSAGEIN_V1
product: Windows
targetos: Windows
req.typenames: RILMESSAGEIN_V1
---

# RILMESSAGEIN_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMESSAGEIN_V1 {
  DWORD       cbSize;
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  DWORD       dwAckID;
  RILMESSAGE  rm;
} RILMESSAGEIN_V1, RILMESSAGEIN_V1;
````

## Members


`cbSize`



`dwExecutor`



`hUiccApp`



`dwAckID`



`rm`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |