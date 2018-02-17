---
UID: NS:rilapitypes.RILUICCTOOLKITCMD
title: RILUICCTOOLKITCMD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicctoolkitcmd_2.htm
old-project: netvista
ms.assetid: d5a50ec7-6b25-4854-9dca-dcd868816735
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILUICCTOOLKITCMD, rilapitypes/RILUICCTOOLKITCMD, netvista.riluicctoolkitcmd_2, RILUICCTOOLKITCMD structure [Network Drivers Starting with Windows Vista], RILUICCTOOLKITCMD"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILUICCTOOLKITCMD
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCTOOLKITCMD, RILUICCTOOLKITCMD"
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
| **Header** | rilapitypes.h |