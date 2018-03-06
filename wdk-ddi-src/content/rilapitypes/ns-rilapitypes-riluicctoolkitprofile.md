---
UID: NS:rilapitypes.RILUICCTOOLKITPROFILE
title: RILUICCTOOLKITPROFILE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicctoolkitprofile_2.htm
old-project: netvista
ms.assetid: 8d8a6c85-474c-4e86-99a9-ac113edbe7b3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE structure [Network Drivers Starting with Windows Vista], netvista.riluicctoolkitprofile_2, rilapitypes/RILUICCTOOLKITPROFILE"
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
-	RILUICCTOOLKITPROFILE
product: Windows
targetos: Windows
req.typenames: RILUICCTOOLKITPROFILE, *LPRILUICCTOOLKITPROFILE
req.product: Windows 10 or later.
---

# RILUICCTOOLKITPROFILE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCTOOLKITPROFILE {
  DWORD    cbSize;
  DWORD    dwProfileSize;
  BYTE [1] bProfile;
} RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE;
````

## Members


`bProfile`



`cbSize`



`dwProfileSize`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |