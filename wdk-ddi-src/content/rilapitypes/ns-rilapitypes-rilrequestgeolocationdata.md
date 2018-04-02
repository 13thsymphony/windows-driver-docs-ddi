---
UID: NS:rilapitypes.RILREQUESTGEOLOCATIONDATA
title: RILREQUESTGEOLOCATIONDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrequestgeolocationdata.htm
old-project: netvista
ms.assetid: 814e00c5-7248-4853-a61b-e70be86bca0e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA, RILREQUESTGEOLOCATIONDATA structure [Network Drivers Starting with Windows Vista], netvista.rilrequestgeolocationdata, ntddrilapitypes/RILREQUESTGEOLOCATIONDATA"
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
-	RILREQUESTGEOLOCATIONDATA
product:
- Windows
targetos: Windows
req.typenames: RILREQUESTGEOLOCATIONDATA, *LPRILREQUESTGEOLOCATIONDATA
req.product: Windows 10 or later.
---

# RILREQUESTGEOLOCATIONDATA structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILREQUESTGEOLOCATIONDATA {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILGEOLOCATIONTYPEMASK        dwLocationInformationMask;
  RILGEOLOCATIONREQUESTACCURACY dwLocationRequestAccuracy;
  RILGEOLOCATIONREQUESTINFO     rrRequestInformation;
}  *LPRILREQUESTGEOLOCATIONDATA;
```

## Members


`cbSize`



`dwParams`



`dwExecutor`



`dwLocationInformationMask`



`dwLocationRequestAccuracy`



`rrRequestInformation`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |