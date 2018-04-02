---
UID: NS:ntddrilapitypes.RILSUPSERVICEDATA
title: RILSUPSERVICEDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupservicedata.htm
old-project: netvista
ms.assetid: 1cb4afae-75ad-4c9b-8b21-f9aade2c5fd8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSUPSERVICEDATA, RILSUPSERVICEDATA, RILSUPSERVICEDATA structure [Network Drivers Starting with Windows Vista], netvista.rilsupservicedata, ntddrilapitypes/RILSUPSERVICEDATA"
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
-	RILSUPSERVICEDATA
product:
- Windows
targetos: Windows
req.typenames: RILSUPSERVICEDATA, *LPRILSUPSERVICEDATA
---

# RILSUPSERVICEDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSUPSERVICEDATA {
  DWORD                   cbSize;
  DWORD                   dwParams;
  DWORD                   dwExecutor;
  RILSUPSERVICEDATASTATUS dwStatus;
  DWORD                   dwNetworkSSErrorCause;
  DWORD                   dwNetworkCCErrorCause;
  DWORD                   dwVendorErrorCause;
  DWORD                   dwDataSize;
  WCHAR                   wszData[1];
} *LPRILSUPSERVICEDATA, RILSUPSERVICEDATA;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwStatus`



`dwNetworkSSErrorCause`



`dwNetworkCCErrorCause`



`dwVendorErrorCause`



`dwDataSize`



`wszData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |