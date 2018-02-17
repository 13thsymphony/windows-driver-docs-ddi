---
UID: NS:rilapitypes.RILSENDUICCTOOLKITENVELOPEPARAMS
title: RILSENDUICCTOOLKITENVELOPEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsenduicctoolkitenvelopeparams_2.htm
old-project: netvista
ms.assetid: 17bf24fe-bee5-4e08-8e3f-b9d4a03e147e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSENDUICCTOOLKITENVELOPEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsenduicctoolkitenvelopeparams_2, rilapitypes/RILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS, *LPRILSENDUICCTOOLKITENVELOPEPARAMS
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
-	RILSENDUICCTOOLKITENVELOPEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDUICCTOOLKITENVELOPEPARAMS, *LPRILSENDUICCTOOLKITENVELOPEPARAMS
req.product: Windows 10 or later.
---

# RILSENDUICCTOOLKITENVELOPEPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDUICCTOOLKITENVELOPEPARAMS {
  DWORD    dwSlotIndex;
  DWORD    dwEnvelopeSize;
  BYTE [1] bEnvelope;
} RILSENDUICCTOOLKITENVELOPEPARAMS, RILSENDUICCTOOLKITENVELOPEPARAMS;
````

## Members


`bEnvelope`



`dwEnvelopeSize`



`dwSlotIndex`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |