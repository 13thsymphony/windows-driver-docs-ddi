---
UID: NS:rilapitypes.RILPOSITIONINFOLTE
title: RILPOSITIONINFOLTE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfolte_2.htm
old-project: netvista
ms.assetid: 4910571e-af1d-4bcf-a2d9-0d5383530171
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE, RILPOSITIONINFOLTE structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfolte_2, rilapitypes/RILPOSITIONINFOLTE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPOSITIONINFOLTE
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOLTE, *LPRILPOSITIONINFOLTE
req.product: Windows 10 or later.
---

# RILPOSITIONINFOLTE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPOSITIONINFOLTE {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwCellID;
  DWORD  dwEARFCN;
  DWORD  dwPhysCellID;
  DWORD  dwTAC;
  LONG   dwRSRP;
  LONG   dwRSRQ;
  DWORD  dwTimingAdvance;
} RILPOSITIONINFOLTE, RILPOSITIONINFOLTE;
````

## Members


`dwParams`



`dwMobileCountryCode`



`dwMobileNetworkCode`



`dwCellID`



`dwEARFCN`



`dwPhysCellID`



`dwTAC`



`dwRSRP`



`dwRSRQ`



`dwTimingAdvance`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |