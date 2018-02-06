---
UID: NS:ntddrilapitypes.RILCALLHANDOVERSTATE
title: RILCALLHANDOVERSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverstate.htm
old-project: netvista
ms.assetid: 1c9fb343-32f1-444e-9328-097da72cd006
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILCALLHANDOVERSTATE, ntddrilapitypes/RILCALLHANDOVERSTATE, netvista.rilcallhandoverstate, RILCALLHANDOVERSTATE structure [Network Drivers Starting with Windows Vista], RILCALLHANDOVERSTATE"
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
-	RILCALLHANDOVERSTATE
product: Windows
targetos: Windows
req.typenames: RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE
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
| **Header** | ntddrilapitypes.h |