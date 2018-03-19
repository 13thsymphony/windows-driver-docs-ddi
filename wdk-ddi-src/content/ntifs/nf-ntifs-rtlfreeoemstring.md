---
UID: NF:ntifs.RtlFreeOemString
title: RtlFreeOemString function
author: windows-driver-content
description: The RtlFreeOemString routine releases storage that was allocated by any of the Rtl..ToOemString routines.
old-location: ifsk\rtlfreeoemstring.htm
old-project: ifsk
ms.assetid: cd9bc03d-1f57-420c-9430-d2d742f654e1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlFreeOemString, RtlFreeOemString routine [Installable File System Drivers], ifsk.rtlfreeoemstring, ntifs/RtlFreeOemString, rtlref_ffc98e3c-a96f-4250-a527-bcd1ba2ce506.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	RtlFreeOemString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlFreeOemString function
The <b>RtlFreeOemString</b> routine releases storage that was allocated by any of the <b>Rtl..ToOemString</b> routines.

## Syntax

````
VOID RtlFreeOemString(
  _Inout_ POEM_STRING OemString
);
````

## Parameters

`OemString`

Pointer to the OEM string buffer that was allocated by a preceding call to <b>RtlUnicodeStringToCountedOemString</b>, <b>RtlUnicodeStringToOemString</b>, <b>RtlUpcaseUnicodeStringToCountedOemString</b>, or <b>RtlUpcaseUnicodeStringToOemString</b>.


## Return Value

None

## Remarks

<b>RtlFreeOemString</b> deallocates memory only for the buffered OEM string. This routine does not free the buffered Unicode string passed in a preceding call to the <b>Rtl..ToOemString</b> routine. 

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

<a href="..\ntifs\nf-ntifs-rtlunicodestringtocountedoemstring.md">RtlUnicodeStringToCountedOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>