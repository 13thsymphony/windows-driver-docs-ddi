---
UID: NS:ntddsysenv._SYSENV_VARIABLE
title: "_SYSENV_VARIABLE"
author: windows-driver-content
description: Stores the name a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request.
old-location: kernel\sysenv_variable.htm
old-project: kernel
ms.assetid: 311A5977-C3F5-4287-B030-00F4BB9C8629
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PSYSENV_VARIABLE, PSYSENV_VARIABLE, PSYSENV_VARIABLE structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE, SYSENV_VARIABLE structure [Kernel-Mode Driver Architecture], _SYSENV_VARIABLE, kernel.sysenv_variable, ntddsysenv/PSYSENV_VARIABLE, ntddsysenv/SYSENV_VARIABLE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddsysenv.h
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
-	Ntddsysenv.h
api_name:
-	SYSENV_VARIABLE
product: Windows
targetos: Windows
req.typenames: SYSENV_VARIABLE, *PSYSENV_VARIABLE
---

# _SYSENV_VARIABLE structure
Stores the name a system environment variable using
    SysEnv device. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a> request.

## Syntax
```
typedef struct _SYSENV_VARIABLE {
  GUID  VendorGuid;
  ULONG VariableNameLength;
  WCHAR VariableName[ANYSIZE_ARRAY];
} SYSENV_VARIABLE, *PSYSENV_VARIABLE;
```

## Members


`VendorGuid`

The vendor GUID.

`VariableNameLength`

The length of the string pointed to by  <b>VariableName</b>, which contains the name of the variable.

`VariableName`

A string that  contains the name of the variable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddsysenv.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a>