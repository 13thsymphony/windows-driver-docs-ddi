---
UID: NS:rilapitypes.RILCALLHANDOVERSTATE
title: RILCALLHANDOVERSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverstate_2.htm
old-project: netvista
ms.assetid: 21558cd6-f200-4867-920f-8aaadc9839f8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLHANDOVERSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallhandoverstate_2, RILCALLHANDOVERSTATE, rilapitypes/RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE
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
-	RILCALLHANDOVERSTATE
product: Windows
targetos: Windows
req.typenames: RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE
req.product: Windows 10 or later.
---

# RILCALLHANDOVERSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLHANDOVERSTATE {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RILCALLHANDOVERPHASE  dwPhase;
  RILCALLTYPE           dwOldType;
  RILCALLTYPE           dwNewType;
  DWORD                 dw3gppCause;
} RILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE;
````

## Members


`cbSize`



`dw3gppCause`



`dwNewType`



`dwOldType`



`dwParams`



`dwPhase`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |