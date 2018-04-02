---
UID: NS:rilapitypes.RILIMSSTATUS_V2
title: RILIMSSTATUS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v2.htm
old-project: netvista
ms.assetid: afc17375-a65d-495d-b68a-b74146cb8f69
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILIMSSTATUS_V2, RILIMSSTATUS_V2, RILIMSSTATUS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilimsstatus_v2, ntddrilapitypes/RILIMSSTATUS_V2"
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
-	RILIMSSTATUS_V2
product: Windows
targetos: Windows
req.typenames: RILIMSSTATUS_V2, *LPRILIMSSTATUS_V2
req.product: Windows 10 or later.
---

# RILIMSSTATUS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILIMSSTATUS_V2 {
  DWORD        cbSize;
  DWORD        dwParams;
  DWORD        dwExecutor;
  HUICCAPP     hUiccApp;
  DWORD        dwAvailableServices;
  RILSMSFORMAT dwSMSSupportedFormat;
  WCHAR        wszServingDomain[256];
}  *LPRILIMSSTATUS_V2;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`hUiccApp`



`dwAvailableServices`



`dwSMSSupportedFormat`



`wszServingDomain`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |