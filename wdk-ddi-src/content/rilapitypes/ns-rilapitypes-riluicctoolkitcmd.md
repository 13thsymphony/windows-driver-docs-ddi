---
UID: NS:rilapitypes.RILUICCTOOLKITCMD
title: RILUICCTOOLKITCMD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicctoolkitcmd.htm
old-project: netvista
ms.assetid: f5fc28df-ee06-4efd-8509-a05ed0ebf322
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILUICCTOOLKITCMD, RILUICCTOOLKITCMD, RILUICCTOOLKITCMD structure [Network Drivers Starting with Windows Vista], netvista.riluicctoolkitcmd, ntddrilapitypes/RILUICCTOOLKITCMD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	RILUICCTOOLKITCMD
product: Windows
targetos: Windows
req.typenames: RILUICCTOOLKITCMD, *LPRILUICCTOOLKITCMD
req.product: Windows 10 or later.
---

# RILUICCTOOLKITCMD structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCTOOLKITCMD {
  DWORD    cbSize;
  DWORD    dwSlotIndex;
  BOOL     fTerminalResponseNeeded;
  DWORD    dwDetailsSize;
  BYTE [1] bDetails;
} RILUICCTOOLKITCMD, RILUICCTOOLKITCMD;
````

## Members


`bDetails`



`cbSize`



`dwDetailsSize`



`dwSlotIndex`



`fTerminalResponseNeeded`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |