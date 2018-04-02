---
UID: NS:rilapitypes.RILCALLFORWARDINGSETTINGS
title: RILCALLFORWARDINGSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettings.htm
old-project: netvista
ms.assetid: 3603bc82-0058-43bd-9d45-90c198a20040
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLFORWARDINGSETTINGS, RILCALLFORWARDINGSETTINGS, RILCALLFORWARDINGSETTINGS structure [Network Drivers Starting with Windows Vista], netvista.rilcallforwardingsettings, ntddrilapitypes/RILCALLFORWARDINGSETTINGS"
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
-	RILCALLFORWARDINGSETTINGS
product: Windows
targetos: Windows
req.typenames: RILCALLFORWARDINGSETTINGS, *LPRILCALLFORWARDINGSETTINGS
req.product: Windows 10 or later.
---

# RILCALLFORWARDINGSETTINGS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLFORWARDINGSETTINGS {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILSERVICESETTINGSSTATUS dwStatus;
  DWORD                    dwInfoClasses;
  RILADDRESS               raAddress;
  RILSUBADDRESS            rsaSubAddress;
  DWORD                    dwDelayTime;
} *LPRILCALLFORWARDINGSETTINGS, RILCALLFORWARDINGSETTINGS;
```

## Members


`cbSize`



`dwParams`



`dwStatus`



`dwInfoClasses`



`raAddress`



`rsaSubAddress`



`dwDelayTime`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |