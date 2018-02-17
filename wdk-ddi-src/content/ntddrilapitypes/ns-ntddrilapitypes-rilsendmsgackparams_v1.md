---
UID: NS:ntddrilapitypes.RILSENDMSGACKPARAMS_V1
title: RILSENDMSGACKPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgackparams_v1.htm
old-project: netvista
ms.assetid: 96f1e6c2-f2cc-44f0-af9c-4a17ab22bdf4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsendmsgackparams_v1, RILSENDMSGACKPARAMS_V1 structure [Network Drivers Starting with Windows Vista], RILSENDMSGACKPARAMS_V1, ntddrilapitypes/RILSENDMSGACKPARAMS_V1
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
-	RILSENDMSGACKPARAMS_V1
product: Windows
targetos: Windows
req.typenames: RILSENDMSGACKPARAMS_V1
---

# RILSENDMSGACKPARAMS_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDMSGACKPARAMS_V1 {
  DWORD            cbSize;
  DWORD            dwExecutor;
  HUICCAPP         hUiccApp;
  DWORD            dwAckID;
  RILMSGACKSTATUS  dwMsgStatus;
} RILSENDMSGACKPARAMS_V1, RILSENDMSGACKPARAMS_V1;
````

## Members


`cbSize`



`dwAckID`



`dwExecutor`



`dwMsgStatus`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |