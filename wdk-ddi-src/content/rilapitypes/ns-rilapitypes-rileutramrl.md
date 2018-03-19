---
UID: NS:rilapitypes.RILEUTRAMRL
title: RILEUTRAMRL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rileutramrl_2.htm
old-project: netvista
ms.assetid: 77a57c67-90ff-489c-a791-56ac0afbec59
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILEUTRAMRL, RILEUTRAMRL, RILEUTRAMRL structure [Network Drivers Starting with Windows Vista], netvista.rileutramrl_2, rilapitypes/RILEUTRAMRL"
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
-	RILEUTRAMRL
product: Windows
targetos: Windows
req.typenames: RILEUTRAMRL, *LPRILEUTRAMRL
req.product: Windows 10 or later.
---

# RILEUTRAMRL structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILEUTRAMRL {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwCellID;
  DWORD  dwEARFCN;
  DWORD  dwPhysCellID;
  DWORD  dwTAC;
  LONG   dwRSRP;
  LONG   dwRSRQ;
} RILEUTRAMRL, RILEUTRAMRL;
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




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |