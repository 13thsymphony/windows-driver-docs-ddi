---
UID: NF:ntifs.RtlUnicodeStringToOemSize
title: RtlUnicodeStringToOemSize macro
author: windows-driver-content
description: The RtlUnicodeStringToOemSize routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string.
old-location: ifsk\rtlunicodestringtooemsize.htm
old-project: ifsk
ms.assetid: 0e648c99-6d1a-4515-af17-a16e88351f45
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUnicodeStringToOemSize, RtlUnicodeStringToOemSize routine [Installable File System Drivers], ifsk.rtlunicodestringtooemsize, ntifs/RtlUnicodeStringToOemSize, rtlref_836e23f0-2e1a-474e-a66c-615f260e2f4f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUnicodeStringToOemSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlUnicodeStringToOemSize function
The <b>RtlUnicodeStringToOemSize</b> routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string.

## Syntax

````
ULONG RtlUnicodeStringToOemSize(
  _In_ PUNICODE_STRING UnicodeString
);
````

## Parameters

`STRING`

TBD


## Return Value

None

## Remarks

<b>RtlUnicodeStringToOemSize</b> can be called to determine how much memory to allocate when translating a Unicode string to OEM characters with <b>RtlUnicodeStringToOemString</b> or <b>RtlUpcaseUnicodeStringToOemString</b>. The returned value includes space for a NULL terminator for the OEM string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtounicodesize.md">RtlOemStringToUnicodeSize</a>