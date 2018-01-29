---
UID : NF:ntifs.RtlMultiByteToUnicodeSize
title : RtlMultiByteToUnicodeSize function
author : windows-driver-content
description : The RtlMultiByteToUnicodeSize routine determines the number of bytes that are required to store the Unicode translation for the specified source string.
old-location : ifsk\rtlmultibytetounicodesize.htm
old-project : ifsk
ms.assetid : f285e319-23ef-4951-8fb3-107cd54a23b3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : rtlref_f2e77505-7c59-4bb2-993f-622ea16a83c6.xml, RtlMultiByteToUnicodeSize, ntifs/RtlMultiByteToUnicodeSize, RtlMultiByteToUnicodeSize routine [Installable File System Drivers], ifsk.rtlmultibytetounicodesize
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


# RtlMultiByteToUnicodeSize function
The <b>RtlMultiByteToUnicodeSize</b> routine determines the number of bytes that are required to store the Unicode translation for the specified source string. The translation is assumed to use the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set.

## Syntax

````
NTSTATUS RtlMultiByteToUnicodeSize(
  _Out_       PULONG BytesInUnicodeString,
  _In_  const CHAR   *MultiByteString,
  _In_        ULONG  BytesInMultiByteString
);
````

## Parameters

`BytesInUnicodeString`

Pointer to a caller-allocated variable that receives the number of bytes that are required to store the translated string.

`MultiByteString`

Pointer to the source string for which the Unicode length is to be calculated.

`BytesInMultiByteString`

Length, in bytes, of the source string.


## Return Value

<b>RtlMultiByteToUnicodeSize</b> returns STATUS_SUCCESS.

## Remarks

<b>RtlMultiByteToUnicodeSize</b> can be called to determine how much memory to allocate, or possibly, the value to specify for <i>MaxBytesInUnicodeString</i>, before translating a multibyte string into Unicode with <b>RtlMultiByteToUnicodeN</b>. The returned value does not include space for a NULL terminator for the Unicode string. 

Like <b>RtlMultiByteToUnicodeN</b>, <b>RtlMultiByteToUnicodeSize</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

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

<a href="..\ntifs\nf-ntifs-rtlmultibytetounicoden.md">RtlMultiByteToUnicodeN</a>

<a href="..\ntifs\nf-ntifs-rtlunicodetomultibytesize.md">RtlUnicodeToMultiByteSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlMultiByteToUnicodeSize routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>