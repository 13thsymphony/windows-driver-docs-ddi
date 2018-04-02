---
UID: NF:wdm.RtlxAnsiStringToUnicodeSize
title: RtlxAnsiStringToUnicodeSize function
author: windows-driver-content
description: The RtlxAnsiStringToUnicodeSize routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.
old-location: kernel\rtlxansistringtounicodesize.htm
old-project: kernel
ms.assetid: 232ac7b0-d949-4db6-a243-b4e5ca0f3cc0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlxAnsiStringToUnicodeSize, RtlxAnsiStringToUnicodeSize routine [Kernel-Mode Driver Architecture], k109_9343d498-bc89-428c-8e68-53c205c58bae.xml, kernel.rtlxansistringtounicodesize, wdm/RtlxAnsiStringToUnicodeSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
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
-	RtlxAnsiStringToUnicodeSize
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlxAnsiStringToUnicodeSize function
The <b>RtlxAnsiStringToUnicodeSize</b> routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.

## Syntax

```
NTSYSAPI ULONG RtlxAnsiStringToUnicodeSize(
  PCANSI_STRING AnsiString
);
```

## Parameters

`AnsiString`

Pointer to the ANSI string for which to compute the number of bytes that are required for an equivalent null-terminated Unicode string.


## Return Value

<b>RtlxAnsiStringToUnicodeSize</b> returns the number of bytes that are required for an equivalent null-terminated Unicode string, if the ANSI string can be translated into an Unicode string by using the current system locale information. Otherwise, this routine returns zero.

## Remarks

The ANSI string is interpreted for the current system locale.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561725">RtlAnsiStringToUnicodeSize</a>