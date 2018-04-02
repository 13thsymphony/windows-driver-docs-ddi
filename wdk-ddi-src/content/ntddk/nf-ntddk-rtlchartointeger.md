---
UID: NF:ntddk.RtlCharToInteger
title: RtlCharToInteger function
author: windows-driver-content
description: The RtlCharToInteger routine converts a single-byte character string to an integer value in the specified base.
old-location: kernel\rtlchartointeger.htm
old-project: kernel
ms.assetid: a08cb12a-c574-4871-9bba-f8f3a766f377
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlCharToInteger, RtlCharToInteger routine [Kernel-Mode Driver Architecture], k109_0c8d9b78-6363-4884-a475-4f402ea3643a.xml, kernel.rtlchartointeger, ntddk/RtlCharToInteger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlCharToInteger
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlCharToInteger function
The <b>RtlCharToInteger</b> routine converts a single-byte character string to an integer value in the specified base.

## Syntax

```
NTSYSAPI NTSTATUS RtlCharToInteger(
  PCSZ   String,
  ULONG  Base,
  PULONG Value
);
```

## Parameters

`String`

Pointer to a null-terminated, single-byte character string.

`Base`

Specifies decimal, binary, octal, or hexadecimal base. If this parameter is not given, the routine will look for 0x, 0o, and 0b prefixes in the input string to determine if the base should be decimal (default), binary, octal, or hexadecimal.

`Value`

Pointer to a location to which the converted value is returned.


## Return Value

<b>RtlCharToInteger</b> returns STATUS_SUCCESS if the given character string is converted. Otherwise, it can return STATUS_INVALID_PARAMETER.

## Remarks

<b>RtlCharToInteger</b> converts ANSI alphanumeric characters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561929">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561941">RtlIntegerToUnicodeString</a>