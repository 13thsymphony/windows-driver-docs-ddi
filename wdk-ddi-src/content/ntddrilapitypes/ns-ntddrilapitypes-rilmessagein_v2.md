---
UID: NS:ntddrilapitypes.RILMESSAGEIN_V2
title: RILMESSAGEIN_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagein_v2.htm
old-project: netvista
ms.assetid: 44d4f693-4aab-4023-88b7-19c1bfcc7e5a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILMESSAGEIN_V2 structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILMESSAGEIN_V2, RILMESSAGEIN, netvista.rilmessagein_v2, *LPRILMESSAGEIN, RILMESSAGEIN_V2
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
-	RILMESSAGEIN_V2
product: Windows
targetos: Windows
req.typenames: RILMESSAGEIN, RILMESSAGEIN_V2, *LPRILMESSAGEIN
---

# RILMESSAGEIN_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMESSAGEIN_V2 {
  DWORD       cbSize;
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  DWORD       dwAckID;
  RILMESSAGE  rm;
  DWORD       dwFlags;
} RILMESSAGEIN_V2, RILMESSAGEIN_V2;
````

## Members


`cbSize`



`dwAckID`



`dwExecutor`



`dwFlags`



`hUiccApp`



`rm`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |