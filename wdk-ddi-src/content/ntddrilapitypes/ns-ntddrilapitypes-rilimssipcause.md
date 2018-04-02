---
UID: NS:ntddrilapitypes.RILIMSSIPCAUSE
title: RILIMSSIPCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssipcause.htm
old-project: netvista
ms.assetid: 79a57fc5-1526-4f18-b51c-7d045092fcb4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILIMSSIPCAUSE, RILIMSSIPCAUSE, RILIMSSIPCAUSE structure [Network Drivers Starting with Windows Vista], netvista.rilimssipcause, ntddrilapitypes/RILIMSSIPCAUSE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILIMSSIPCAUSE
product:
- Windows
targetos: Windows
req.typenames: RILIMSSIPCAUSE, *LPRILIMSSIPCAUSE
---

# RILIMSSIPCAUSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILIMSSIPCAUSE {
  DWORD dwCauseValue;
  DWORD dwReasonValue;
} *LPRILIMSSIPCAUSE, RILIMSSIPCAUSE;
```

## Members


`dwCauseValue`



`dwReasonValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |