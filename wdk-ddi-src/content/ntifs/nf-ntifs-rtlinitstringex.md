---
UID: NF:ntifs.RtlInitStringEx
title: RtlInitStringEx function
author: windows-driver-content
description: The RtlInitStringEx routine initializes a counted string of 8-bit characters.
old-location: kernel\rtl_init_string_ex.htm
old-project: kernel
ms.assetid: D59E6B78-2B51-4A5D-A9EA-E6D8DD90C374
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlInitString, RtlInitString routine [Kernel-Mode Driver Architecture], RtlInitStringEx, kernel.rtl_init_string_ex, wdm/RtlInitString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInitString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlInitStringEx function
The <b>RtlInitStringEx</b> routine initializes a counted string of 8-bit characters.

## Syntax

```
NTSYSAPI NTSTATUS RtlInitStringEx(
  PSTRING               DestinationString,
  __drv_aliasesMem PCSZ SourceString
);
```

## Parameters

`DestinationString`

A pointer to the <b>STRING</b> structure to be initialized. The Ntdef.h header file defines this structure to be identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure.

`SourceString`

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## Return Value

Returns STATUS_NAME_TOO_LONG if the SourceString is too long. Otherwise, this routine returns STATUS_SUCCESS.

## Remarks

This routine initializes a counted character string.

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <b>STRING</b> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitStringEx</b> does not alter the source string pointed to by <i>SourceString</i>.

Callers of <b>RtlInitStringEx</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>