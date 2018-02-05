---
UID : NF:ntifs.RtlMultiByteToUnicodeN
title : RtlMultiByteToUnicodeN function
author : windows-driver-content
description : The RtlMultiByteToUnicodeN routine translates the specified source string into a Unicode string, using the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set.
old-location : ifsk\rtlmultibytetounicoden.htm
old-project : ifsk
ms.assetid : c0cc4fba-01ba-4745-8dee-fc4c43f570cf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlMultiByteToUnicodeN routine [Installable File System Drivers], rtlref_c9245403-e17c-479b-ac16-07deb29a56d1.xml, ntifs/RtlMultiByteToUnicodeN, ifsk.rtlmultibytetounicoden, RtlMultiByteToUnicodeN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : "< DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# RtlMultiByteToUnicodeN function
The <b>RtlMultiByteToUnicodeN</b> routine translates the specified source string into a Unicode string, using the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set.

## Syntax

````
NTSTATUS RtlMultiByteToUnicodeN(
  _Out_           PWCH   UnicodeString,
  _In_            ULONG  MaxBytesInUnicodeString,
  _Out_opt_       PULONG BytesInUnicodeString,
  _In_      const CHAR   *MultiByteString,
  _In_            ULONG  BytesInMultiByteString
);
````

## Parameters

`UnicodeString`

Pointer to a caller-allocated buffer that receives the translated string. <i>UnicodeString</i> buffer must not overlap with <i>MultiByteString </i>buffer.

`MaxBytesInUnicodeString`

Maximum number of bytes to be written at <i>UnicodeString</i>. If this value causes the translated string to be truncated, <b>RtlMultiByteToUnicodeN</b> does not return an error status.

`BytesInUnicodeString`

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter can be <b>NULL</b>.

`MultiByteString`

Pointer to the string to be translated.

`BytesInMultiByteString`

Size, in bytes, of the string at <i>MultiByteString</i>.


## Return Value

<b>RtlMultiByteToUnicodeN</b> returns STATUS_SUCCESS.

## Remarks

<b>RtlMultiByteToUnicodeN</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

Although <i>BytesInUnicodeString</i> is optional and can be <b>NULL</b>, callers should provide storage for it, because the received length can be used to determine whether the conversion was successful.

If the current system code page defines a single-byte character set, all ANSI characters in the range 0x00 to 0x7f are simply zero-extended in the corresponding Unicode string to speed the conversion operation. The ANSI value 0x5c in such a code page is translated into the backslash character, even if the current single-byte code page defines this character as the Yen sign. 

<b>RtlMultiByteToUnicodeN</b> does not modify the source string unless the <i>UnicodeString</i> and <i>MultiByteString</i> pointers are equivalent. The returned Unicode string is not null-terminated. 

Like <b>RtlMultiByteToUnicodeSize</b>, <b>RtlMultiByteToUnicodeN</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtlunicodetomultibyten.md">RtlUnicodeToMultiByteN</a>

<a href="..\ntifs\nf-ntifs-rtlmultibytetounicodesize.md">RtlMultiByteToUnicodeSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlMultiByteToUnicodeN routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>