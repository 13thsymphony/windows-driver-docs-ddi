---
UID: NS:ntddsysenv._SYSENV_VARIABLE_INFO
title: "_SYSENV_VARIABLE_INFO"
author: windows-driver-content
description: Stores the information about a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_QUERY_VARIABLE_INFO request.
old-location: kernel\sysenv_variable_info.htm
old-project: kernel
ms.assetid: D9C7BB96-1E26-4D89-9CBE-074232FD0752
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PSYSENV_VARIABLE_INFO, PSYSENV_VARIABLE_INFO, PSYSENV_VARIABLE_INFO structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE_INFO, SYSENV_VARIABLE_INFO structure [Kernel-Mode Driver Architecture], _SYSENV_VARIABLE_INFO, kernel.sysenv_variable_info, ntddsysenv/PSYSENV_VARIABLE_INFO, ntddsysenv/SYSENV_VARIABLE_INFO"
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
-	SYSENV_VARIABLE_INFO
product: Windows
targetos: Windows
req.typenames: SYSENV_VARIABLE_INFO, *PSYSENV_VARIABLE_INFO
---

# _SYSENV_VARIABLE_INFO structure
Stores the information about a system environment variable using
    SysEnv device. This structure is used in the <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_query_variable_info.md">IOCTL_SYSENV_QUERY_VARIABLE_INFO</a> request.

## Syntax
````
typedef struct _SYSENV_VARIABLE_INFO {
  ULONGLONG MaximumVariableStorageSize;
  ULONGLONG RemainingVariableStorageSize;
  ULONGLONG MaximumVariableSize;
} SYSENV_VARIABLE_INFO, *PSYSENV_VARIABLE_INFO;
````

## Members


`MaximumVariableStorageSize`

The size of the variable.

`RemainingVariableStorageSize`

The remaining size of the variable.

`MaximumVariableSize`

The maximum size of the variable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddsysenv.h |

## See Also

<a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_query_variable_info.md">IOCTL_SYSENV_QUERY_VARIABLE_INFO</a>