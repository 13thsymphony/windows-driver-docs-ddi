---
UID: NS:rilapitypes.RILCALLHANDOVERSTATE
title: RILCALLHANDOVERSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverstate.htm
old-project: netvista
ms.assetid: 1c9fb343-32f1-444e-9328-097da72cd006
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallhandoverstate, ntddrilapitypes/RILCALLHANDOVERSTATE"
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
-	RILCALLHANDOVERSTATE
product: Windows
targetos: Windows
req.typenames: RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE
req.product: Windows 10 or later.
---

# RILCALLHANDOVERSTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLHANDOVERSTATE {
  DWORD                cbSize;
  DWORD                dwParams;
  RILCALLHANDOVERPHASE dwPhase;
  RILCALLTYPE          dwOldType;
  RILCALLTYPE          dwNewType;
  DWORD                dw3gppCause;
} *LPRILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE;
```

## Members


`cbSize`



`dwParams`



`dwPhase`



`dwOldType`



`dwNewType`



`dw3gppCause`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |