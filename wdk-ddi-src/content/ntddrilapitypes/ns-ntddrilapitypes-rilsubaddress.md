---
UID: NS:ntddrilapitypes.RILSUBADDRESS
title: RILSUBADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddress.htm
old-project: netvista
ms.assetid: 0a1f9e89-df17-4802-9685-06a2eedbc0e5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILSUBADDRESS, RILSUBADDRESS, RILSUBADDRESS structure [Network Drivers Starting with Windows Vista], netvista.rilsubaddress, ntddrilapitypes/RILSUBADDRESS"
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
-	RILSUBADDRESS
product: Windows
targetos: Windows
req.typenames: RILSUBADDRESS, *LPRILSUBADDRESS
---

# RILSUBADDRESS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILSUBADDRESS {
  DWORD             cbSize;
  DWORD             dwParams;
  RILSUBADDRESSTYPE dwType;
  WCHAR             wszSubAddress[256];
}  *LPRILSUBADDRESS;
```

## Members


`cbSize`



`dwParams`



`dwType`



`wszSubAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |