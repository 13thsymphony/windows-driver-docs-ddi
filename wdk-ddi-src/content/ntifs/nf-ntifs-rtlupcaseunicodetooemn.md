---
UID: NF:ntifs.RtlUpcaseUnicodeToOemN
title: RtlUpcaseUnicodeToOemN function
author: windows-driver-content
description: The RtlUpcaseUnicodeToOemN routine translates a given Unicode string into an uppercase OEM string, using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodetooemn.htm
old-project: ifsk
ms.assetid: d4d802c1-66e9-4342-ba7d-d9e5a464362e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlUpcaseUnicodeToOemN, RtlUpcaseUnicodeToOemN routine [Installable File System Drivers], ifsk.rtlupcaseunicodetooemn, ntifs/RtlUpcaseUnicodeToOemN, rtlref_b1fcf08b-c13f-4b60-a570-f4bffe730ba4.xml
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
-	RtlUpcaseUnicodeToOemN
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlUpcaseUnicodeToOemN function
The <b>RtlUpcaseUnicodeToOemN</b> routine translates a given Unicode string into an uppercase OEM string, using the current system OEM code page.

## Syntax

```
NTSYSAPI NTSTATUS RtlUpcaseUnicodeToOemN(
  PCHAR  OemString,
  ULONG  MaxBytesInOemString,
  PULONG BytesInOemString,
  PCWCH  UnicodeString,
  ULONG  BytesInUnicodeString
);
```

## Parameters

`OemString`

Pointer to a caller-allocated buffer to receive the translated string.

`MaxBytesInOemString`

Maximum number of bytes to be written to <i>OemString</i>.

`BytesInOemString`

Pointer to a caller-allocated variable that receives the number of bytes in the translated string. This parameter can be <b>NULL</b>.

`UnicodeString`

Pointer to the Unicode source string to be translated.

`BytesInUnicodeString`

Size, in bytes, of the string at <i>UnicodeString</i>.


## Return Value

<b>RtlUnicodeToOemN</b> returns STATUS_SUCCESS if the full string at <i>UnicodeString</i> was successfully translated, converted to uppercase, and returned at <i>OemString</i>. Otherwise, it can return STATUS_BUFFER_OVERFLOW if the destination string must be truncated to fit the given <i>MaxBytesInOemString</i>.

## Remarks

For the return value STATUS_BUFFER_OVERFLOW, the truncated string at <i>OemString</i> was translated without error. 

For the return value STATUS_SUCCESS, the value at <i>BytesInOemString</i>, if any, indicates the length of the returned string, rather than the given <i>MaxBytesInOemString</i>. 

This routine does not modify the source string. It returns a null-terminated OEM string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInOemString</i> did not cause truncation.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553254">RtlUnicodeStringToOemSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553272">RtlUnicodeToOemN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553277">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553282">RtlUpcaseUnicodeStringToOemString</a>