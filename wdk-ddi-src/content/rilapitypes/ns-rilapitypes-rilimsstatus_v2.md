---
UID: NS:rilapitypes.RILIMSSTATUS_V2
title: RILIMSSTATUS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v2_2.htm
old-project: netvista
ms.assetid: 44aa62ac-510b-4f6d-9f17-f4abeadb06c1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILIMSSTATUS_V2 structure [Network Drivers Starting with Windows Vista], *LPRILIMSSTATUS_V2, rilapitypes/RILIMSSTATUS_V2, netvista.rilimsstatus_v2_2, RILIMSSTATUS_V2
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
-	RILIMSSTATUS_V2
product: Windows
targetos: Windows
req.typenames: "*LPRILIMSSTATUS_V2, RILIMSSTATUS_V2"
req.product: Windows 10 or later.
---

# RILIMSSTATUS_V2 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILIMSSTATUS_V2 {
  DWORD                     cbSize;
  DWORD                     dwParams;
  DWORD                     dwExecutor;
  HUICCAPP                  hUiccApp;
  DWORD                     dwAvailableServices;
  RILSMSFORMAT              dwSMSSupportedFormat;
  WCHAR [MAXLENGTH_ADDRESS] wszServingDomain;
} RILIMSSTATUS_V2, RILIMSSTATUS_V2;
````

## Members


`cbSize`



`dwAvailableServices`



`dwExecutor`



`dwParams`



`dwSMSSupportedFormat`



`hUiccApp`



`wszServingDomain`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |