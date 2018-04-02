---
UID: NF:ntddk.RtlUpperChar
title: RtlUpperChar function
author: windows-driver-content
description: The RtlUpperChar routine converts the specified character to uppercase.
old-location: kernel\rtlupperchar.htm
old-project: kernel
ms.assetid: a87e9f52-a136-492e-bfb3-dfbbea8b79e0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUpperChar, RtlUpperChar routine [Kernel-Mode Driver Architecture], k109_c1a13e9a-f863-4bcd-ae89-daee0c3d3a4b.xml, kernel.rtlupperchar, ntddk/RtlUpperChar
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUpperChar
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlUpperChar function
The <b>RtlUpperChar</b> routine converts the specified character to uppercase.

## Syntax

```
NTSYSAPI CHAR RtlUpperChar(
  CHAR Character
);
```

## Parameters

`Character`

Specifies the character to convert.


## Return Value

<b>RtlUpperChar</b> returns the uppercase version of the specified character or returns the value specified by the caller for <i>Character</i> if the specified character cannot be converted.

## Remarks

<b>RtlUpperChar</b> returns the input <i>Character</i> unconverted if it is the lead byte of a multibyte character or if the uppercase equivalent of <i>Character</i> is a double-byte character. To convert such characters, use <b>RtlUpcaseUnicodeChar</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563003">RtlUpcaseUnicodeChar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563013">RtlUpperString</a>