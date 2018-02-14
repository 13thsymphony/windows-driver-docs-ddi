---
UID: NS:ntddrilapitypes.RILSUPSERVICEDATA
title: RILSUPSERVICEDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupservicedata.htm
old-project: netvista
ms.assetid: 1cb4afae-75ad-4c9b-8b21-f9aade2c5fd8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSUPSERVICEDATA, ntddrilapitypes/RILSUPSERVICEDATA, RILSUPSERVICEDATA structure [Network Drivers Starting with Windows Vista], *LPRILSUPSERVICEDATA, netvista.rilsupservicedata
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
-	RILSUPSERVICEDATA
product: Windows
targetos: Windows
req.typenames: RILSUPSERVICEDATA, *LPRILSUPSERVICEDATA
---

# RILSUPSERVICEDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSUPSERVICEDATA {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  RILSUPSERVICEDATASTATUS  dwStatus;
  DWORD                    dwNetworkSSErrorCause;
  DWORD                    dwNetworkCCErrorCause;
  DWORD                    dwVendorErrorCause;
  DWORD                    dwDataSize;
  WCHAR [1]                wszData;
} RILSUPSERVICEDATA, RILSUPSERVICEDATA;
````

## Members


`cbSize`



`dwDataSize`



`dwExecutor`



`dwNetworkCCErrorCause`



`dwNetworkSSErrorCause`



`dwParams`



`dwStatus`



`dwVendorErrorCause`



`wszData`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |