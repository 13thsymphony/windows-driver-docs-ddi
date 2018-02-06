---
UID: NS:ntddrilapitypes.RILSENDMSGACKPARAMS_V2
title: RILSENDMSGACKPARAMS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgackparams_v2.htm
old-project: netvista
ms.assetid: 3c05c1a0-339e-447f-b0df-18303ee63f98
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSENDMSGACKPARAMS_V2, netvista.rilsendmsgackparams_v2, ntddrilapitypes/RILSENDMSGACKPARAMS_V2, *LPRILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS_V2 structure [Network Drivers Starting with Windows Vista], RILSENDMSGACKPARAMS
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
-	RILSENDMSGACKPARAMS_V2
product: Windows
targetos: Windows
req.typenames: RILSENDMSGACKPARAMS_V2, *LPRILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS
---

# RILSENDMSGACKPARAMS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDMSGACKPARAMS_V2 {
  DWORD            cbSize;
  DWORD            dwExecutor;
  HUICCAPP         hUiccApp;
  DWORD            dwAckID;
  RILMSGACKSTATUS  dwMsgStatus;
  RILSMSFORMAT     dwSmsFormat;
  DWORD            dwOptions;
} RILSENDMSGACKPARAMS_V2, RILSENDMSGACKPARAMS_V2;
````

## Members


`cbSize`



`dwAckID`



`dwExecutor`



`dwMsgStatus`



`dwOptions`



`dwSmsFormat`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |