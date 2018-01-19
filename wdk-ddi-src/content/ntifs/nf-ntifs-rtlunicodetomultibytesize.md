---
UID : NF:ntifs.RtlUnicodeToMultiByteSize
title : RtlUnicodeToMultiByteSize function
author : windows-driver-content
description : The RtlUnicodeToMultiByteSize routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP).
old-location : ifsk\rtlunicodetomultibytesize.htm
old-project : ifsk
ms.assetid : 603a5554-2e61-49f1-a4b1-e0f0f3ba36c8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlUnicodeToMultiByteSize
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
req.alt-api : RtlUnicodeToMultiByteSize
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : < DISPATCH_LEVEL
req.typenames : TOKEN_TYPE
---


# RtlUnicodeToMultiByteSize function
The <b>RtlUnicodeToMultiByteSize</b> routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP).

## Syntax

````
NTSTATUS RtlUnicodeToMultiByteSize(
  _Out_ PULONG BytesInMultiByteString,
  _In_  PCWCH  UnicodeString,
  _In_  ULONG  BytesInUnicodeString
);
````

## Parameters

`BytesInMultiByteString`

Pointer to a caller-allocated variable that receives the number of bytes required to store the translated string.

`UnicodeString`

Pointer to the Unicode string for which the multibyte length is to be calculated.

`BytesInUnicodeString`

Length, in bytes, of the source string.


## Return Value

<b>RtlUnicodeToMultiByteSize</b> returns STATUS_SUCCESS.

## Remarks

<b>RtlUnicodeToMultiByteSize</b> can be called to determine how much memory to allocate, or possibly the value to specify for <i>MaxBytesInMultiByteString</i>, before translating a Unicode string to ANSI with <b>RtlUnicodeToMultiByteN</b> or <b>RtlUpcaseUnicodeToMultiByteN</b>. The returned value does not include space for a NULL terminator for the ANSI string. 

Like <b>RtlUnicodeToMultiByteN</b>, <b>RtlUnicodeToMultiByteSize</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlmultibytetounicodesize.md">RtlMultiByteToUnicodeSize</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodetomultibyten.md">RtlUnicodeToMultiByteN</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlupcaseunicodetomultibyten.md">RtlUpcaseUnicodeToMultiByteN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUnicodeToMultiByteSize routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>