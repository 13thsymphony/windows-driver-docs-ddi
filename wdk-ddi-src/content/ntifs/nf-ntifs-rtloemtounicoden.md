---
UID: NF:ntifs.RtlOemToUnicodeN
title: RtlOemToUnicodeN function
author: windows-driver-content
description: The RtlOemToUnicodeN routine translates the specified source string into a Unicode string, using the current system OEM code page.
old-location: ifsk\rtloemtounicoden.htm
old-project: ifsk
ms.assetid: fe00b980-4bb5-4ad7-84c0-99d47d2f7c51
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlOemToUnicodeN, RtlOemToUnicodeN routine [Installable File System Drivers], ifsk.rtloemtounicoden, ntifs/RtlOemToUnicodeN, rtlref_7159eedf-5a97-4dc5-a9e8-c4a7f2ac2ee2.xml
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
-	RtlOemToUnicodeN
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlOemToUnicodeN function
The <b>RtlOemToUnicodeN</b> routine translates the specified source string into a Unicode string, using the current system OEM code page.

## Syntax

```
NTSYSAPI NTSTATUS RtlOemToUnicodeN(
  PWCH   UnicodeString,
  ULONG  MaxBytesInUnicodeString,
  PULONG BytesInUnicodeString,
  PCCH   OemString,
  ULONG  BytesInOemString
);
```

## Parameters

`UnicodeString`

Pointer to a caller-allocated buffer that receives the translated string.

`MaxBytesInUnicodeString`

Maximum number of bytes to be written at <i>UnicodeString</i>. If this value causes the translated string to be truncated, <b>RtlOemToUnicodeN</b> does not return an error status.

`BytesInUnicodeString`

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter can be <b>NULL</b>.

`OemString`

Pointer to the OEM source string to be translated into Unicode. If the current code page describes a single-byte character set, this pointer can be the same address as <i>UnicodeString</i>.

`BytesInOemString`

Length, in bytes, of the string at <i>OemString</i>.


## Return Value

<b>RtlOemToUnicodeN</b> returns STATUS_SUCCESS if the full string at <i>OemString</i> was successfully translated and returned at <i>UnicodeString</i>. Otherwise, it can return STATUS_BUFFER_OVERFLOW if the destination string must be truncated to fit the given <i>MaxBytesInUnicodeString</i>. STATUS_BUFFER_OVERFLOW is a warning NTSTATUS value.

## Remarks

<b>RtlOemToUnicodeN</b> supports only precomposed Unicode characters that are mapped to the current system OEM code page installed at system boot time. 

If the current system code page defines a single-byte character set, all single-byte characters in the range 0x00 to 0x7f are simply zero-extended in the corresponding Unicode string to speed the conversion operation. The character value 0x5c in such a code page is translated into the backslash character, even if the current code page defines this character as the Yen sign. 

For the return value STATUS_SUCCESS, the value of <i>BytesInUnicodeString</i>, if any, indicates the length of the returned Unicode string, rather than the given <i>MaxBytesInUnicodeString</i>. 

This routine does not modify the source string unless the <i>UnicodeString</i> and <i>OemString</i> pointers are equivalent. The returned Unicode string is null-terminated if it is not truncated. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553153">RtlOemStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553272">RtlUnicodeToOemN</a>