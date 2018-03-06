---
UID: NS:rilapitypes.RILSENDMSGACKPARAMS_V2
title: RILSENDMSGACKPARAMS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgackparams_v2_2.htm
old-project: netvista
ms.assetid: 10bd2f88-ad1e-4d48-a338-e49c82a66d7a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS, RILSENDMSGACKPARAMS_V2, RILSENDMSGACKPARAMS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilsendmsgackparams_v2_2, rilapitypes/RILSENDMSGACKPARAMS_V2"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSENDMSGACKPARAMS_V2
product: Windows
targetos: Windows
req.typenames: RILSENDMSGACKPARAMS_V2, RILSENDMSGACKPARAMS, *LPRILSENDMSGACKPARAMS
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |