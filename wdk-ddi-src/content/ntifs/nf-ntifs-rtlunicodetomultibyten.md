---
UID : NF:ntifs.RtlUnicodeToMultiByteN
title : RtlUnicodeToMultiByteN function
author : windows-driver-content
description : The RtlUnicodeToMultiByteN routine translates the specified Unicode string into a new character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set.
old-location : ifsk\rtlunicodetomultibyten.htm
old-project : ifsk
ms.assetid : e50199d2-948d-4572-8688-89d92961f85b
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ntifs/RtlUnicodeToMultiByteN, RtlUnicodeToMultiByteN, RtlUnicodeToMultiByteN routine [Installable File System Drivers], ifsk.rtlunicodetomultibyten, rtlref_233ec1ac-8ecc-4261-8f17-11485d03ec50.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Fltkernel.h, Ntifs.h
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
req.dll : NtosKrnl.exe
req.irql : "< DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# RtlUnicodeToMultiByteN function
The <b>RtlUnicodeToMultiByteN</b> routine translates the specified Unicode string into a new character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set.

## Syntax

````
NTSTATUS RtlUnicodeToMultiByteN(
  _Out_     PCHAR  MultiByteString,
  _In_      ULONG  MaxBytesInMultiByteString,
  _Out_opt_ PULONG BytesInMultiByteString,
  _In_      PCWCH  UnicodeString,
  _In_      ULONG  BytesInUnicodeString
);
````

## Parameters

`MultiByteString`

Pointer to a caller-allocated buffer to receive the translated string. <i>MultiByteString </i>buffer must not overlap with <i>UnicodeString </i>buffer.

`MaxBytesInMultiByteString`

Maximum number of bytes to be written to <i>MultiByteString</i>. If this value causes the translated string to be truncated, <b>RtlUnicodeToMultiByteN</b> does not return an error status.

`BytesInMultiByteString`

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter is optional and can be <b>NULL</b>.

`UnicodeString`

Pointer to the Unicode source string to be translated.

`BytesInUnicodeString`

Size, in bytes, of the string at <i>UnicodeString</i>.


## Return Value

<b>RtlUnicodeToMultiByteN</b> returns STATUS_SUCCESS.

## Remarks

<b>RtlUnicodeToMultiByteN</b> translates the given Unicode string using the current system ANSI code page that was installed at system boot time. 

Although <i>BytesInMultiByteString</i> is optional and can be <b>NULL</b>, callers should provide storage for it, because the received length can be used to determine whether the conversion was successful.

This routine does not modify the source string. It returns a null-terminated multibyte string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInMultiByteString</i> did not cause truncation. 

Like <b>RtlUnicodeToMultiByteSize</b>, <b>RtlUnicodeToMultiByteN</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Fltkernel.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | "< DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\nf-ntifs-rtlunicodetomultibytesize.md">RtlUnicodeToMultiByteSize</a>

<a href="..\ntifs\nf-ntifs-rtlmultibytetounicoden.md">RtlMultiByteToUnicodeN</a>

<a href="..\ntifs\nf-ntifs-rtlupcaseunicodetomultibyten.md">RtlUpcaseUnicodeToMultiByteN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUnicodeToMultiByteN routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>