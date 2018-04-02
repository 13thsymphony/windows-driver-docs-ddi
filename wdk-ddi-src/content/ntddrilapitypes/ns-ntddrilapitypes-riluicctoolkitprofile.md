---
UID: NS:ntddrilapitypes.RILUICCTOOLKITPROFILE
title: RILUICCTOOLKITPROFILE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicctoolkitprofile.htm
old-project: netvista
ms.assetid: ff1f5839-78be-48ab-9c26-f8fee6788d51
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE structure [Network Drivers Starting with Windows Vista], netvista.riluicctoolkitprofile, ntddrilapitypes/RILUICCTOOLKITPROFILE"
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
-	RILUICCTOOLKITPROFILE
product:
- Windows
targetos: Windows
req.typenames: RILUICCTOOLKITPROFILE, *LPRILUICCTOOLKITPROFILE
---

# RILUICCTOOLKITPROFILE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUICCTOOLKITPROFILE {
  DWORD cbSize;
  DWORD dwProfileSize;
  BYTE  bProfile[1];
}  *LPRILUICCTOOLKITPROFILE;
```

## Members


`cbSize`



`dwProfileSize`



`bProfile`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |