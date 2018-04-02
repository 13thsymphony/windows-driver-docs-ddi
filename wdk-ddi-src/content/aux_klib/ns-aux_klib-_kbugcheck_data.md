---
UID: NS:aux_klib._KBUGCHECK_DATA
title: "_KBUGCHECK_DATA"
author: windows-driver-content
description: The KBUGCHECK_DATA structure contains bug check parameters.
old-location: kernel\kbugcheck_data.htm
old-project: kernel
ms.assetid: 9fecf57b-e77a-458e-80ce-118eed2d48b4
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKBUGCHECK_DATA, KBUGCHECK_DATA, KBUGCHECK_DATA structure [Kernel-Mode Driver Architecture], PKBUGCHECK_DATA, PKBUGCHECK_DATA structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_DATA, aux_klib/KBUGCHECK_DATA, aux_klib/PKBUGCHECK_DATA, aux_klib_ced3c2df-3d09-45d8-8ae8-049d2bc46160.xml, kernel.kbugcheck_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: aux_klib.h
req.include-header: Aux_klib.h
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
-	aux_klib.h
api_name:
-	KBUGCHECK_DATA
product: Windows
targetos: Windows
req.typenames: KBUGCHECK_DATA, *PKBUGCHECK_DATA
---

# _KBUGCHECK_DATA structure
The <b>KBUGCHECK_DATA</b> structure contains bug check parameters.

## Syntax
```
typedef struct _KBUGCHECK_DATA {
  ULONG     BugCheckDataSize;
  ULONG     BugCheckCode;
  ULONG_PTR Parameter1;
  ULONG_PTR Parameter2;
  ULONG_PTR Parameter3;
  ULONG_PTR Parameter4;
} KBUGCHECK_DATA, *PKBUGCHECK_DATA;
```

## Members


`BugCheckDataSize`

The size, in bytes, of the <b>KBUGCHECK_DATA</b> structure. Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540630">AuxKlibGetBugCheckData</a> must supply this value.

`BugCheckCode`

The bug check code. This value identifies that type of bug check that has occurred.

`Parameter1`

Bug check parameter 1. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter2`

Bug check parameter 2. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter3`

Bug check parameter 3. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

`Parameter4`

Bug check parameter 4. For more information about this parameter, see specific <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a>.

## Remarks
The <b>KBUGCHECK_DATA</b> structure is used as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540630">AuxKlibGetBugCheckData</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | aux_klib.h (include Aux_klib.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540630">AuxKlibGetBugCheckData</a>