---
UID : NF:ntstrsafe.RtlStringCchVPrintfW
title : RtlStringCchVPrintfW function
author : windows-driver-content
description : The RtlStringCchVPrintfW and RtlStringCchVPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location : kernel\rtlstringcchvprintf.htm
old-project : kernel
ms.assetid : a3552042-15e6-4778-8026-a4b615228dc7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlStringCchVPrintfW
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntstrsafe.h
req.include-header : Ntstrsafe.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlStringCchVPrintfW,RtlStringCchVPrintfA,RtlStringCchVPrintfW
req.alt-loc : Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance : 
req.unicode-ansi : RtlStringCchVPrintfW (Unicode) and RtlStringCchVPrintfA (ANSI)
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ntstrsafe.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE"
---


# RtlStringCchVPrintfW function
The <b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.

## Syntax

````
NTSTATUS RtlStringCchVPrintfW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cchDest,
  _In_  LPCTSTR pszFormat,
  _In_  va_list argList
);
````

## Parameters

`pszDest`

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the arguments supplied by <i>argList</i>.

`cchDest`

The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.

`pszFormat`

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives.

`argList`

A <b>va_list</b>-typed argument list. Arguments contained in the argument list will be interpreted by using the formatting string that is supplied by <i>pszFormat</i>.


## Return Value

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the created string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

## Remarks

<b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> should be used instead of the following functions: 

<b>vsprintf</b>

<b>vswprintf</b>

_<b>vsnprintf</b>

_<b>vsnwprintf</b>

All of these functions accept a format string and its arguments, which are provided as a <b>va_list</b>-typed argument list, and return a formatted string. <b>RtlStringCchVPrintfW</b> and <b>RtlStringCchVPrintfA</b> receive the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.

Use <b>RtlStringCchVPrintfW</b> to handle Unicode strings and <b>RtlStringCchVPrintfA</b> to handle ANSI strings. The form you  use depends on your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCchVPrintfW</b>

<b>char</b>

"string"

<b>RtlStringCchVPrintfA</b>

If <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings, or if any argument strings overlap, the behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfexw.md">RtlStringCchVPrintfEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbvprintfw.md">RtlStringCbVPrintf</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchprintfw.md">RtlStringCchPrintf</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchvprintfexw.md">RtlStringCchVPrintfEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchVPrintfW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>