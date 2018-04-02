---
UID: NS:rilapitypes.RILPHONEBOOKADDITIONALNUMBERSTRING
title: RILPHONEBOOKADDITIONALNUMBERSTRING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberstring.htm
old-project: netvista
ms.assetid: 1d201c4d-606d-4461-ad3d-df48d3455724
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookadditionalnumberstring, ntddrilapitypes/RILPHONEBOOKADDITIONALNUMBERSTRING"
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
-	RILPHONEBOOKADDITIONALNUMBERSTRING
product:
- Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBERSTRING, *LPRILPHONEBOOKADDITIONALNUMBERSTRING
req.product: Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBERSTRING structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILPHONEBOOKADDITIONALNUMBERSTRING {
  DWORD cbSize;
  DWORD dwNumId;
  WCHAR wszText[256];
}  *LPRILPHONEBOOKADDITIONALNUMBERSTRING;
```

## Members


`cbSize`



`dwNumId`



`wszText`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |