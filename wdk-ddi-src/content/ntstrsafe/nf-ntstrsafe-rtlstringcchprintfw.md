---
UID: NF.ntstrsafe.RtlStringCchPrintfW
title: RtlStringCchPrintfW function
author: windows-driver-content
description: The RtlStringCchPrintfW and RtlStringCchPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcchprintf.htm
old-project: kernel
ms.assetid: e1c04e73-3055-4de8-bd8d-8d0a13541612
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlStringCchPrintfW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlStringCchPrintfW,RtlStringCchPrintfA,RtlStringCchPrintfW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchPrintfW (Unicode) and RtlStringCchPrintfA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# RtlStringCchPrintfW function



## -description
The <b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.



## -syntax

````
NTSTATUS RtlStringCchPrintfW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cchDest,
  _In_  LPCTSTR pszFormat,
                ...
);
````


## -parameters

### -param pszDest [out]

A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list.


### -param cchDest [in]

The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is <b>NTSTRSAFE_MAX_CCH</b>. 


### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="http://msdn.microsoft.com/en-us/library/56e442dc.aspx">formatting directives</a>.


### -param ... 

A list of arguments that are interpreted by the function, based on formatting directives contained in the <i>pszFormat</i> string.


## -returns
The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the string was created without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the output string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> should be used instead of the following functions:

<b>sprintf</b>

<b>swprintf</b>

_<b>snprintf</b>

_<b>snwprintf</b>

All of these functions accept a format string and a list of arguments and return a formatted string. <b>RtlStringCchPrintfW</b> and <b>RtlStringCchPrintfA</b> accept the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

Use <b>RtlStringCchPrintfW</b> to handle Unicode strings and <b>RtlStringCchPrintfA</b> to handle ANSI strings. The form you use depends on your data.

WCHAR

L"string"

<b>RtlStringCchPrintfW</b>

<b>char</b>

"string"

<b>RtlStringCchPrintfA</b>

If  <i>pszDest </i>and <i>pszFormat</i> point to overlapping strings, or if any argument strings overlap, behavior of the function is undefined.

Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="kernel.rtlstringcchprintfex">RtlStringCchPrintfEx</a>.

The following example shows a simple use of <b>RtlStringCchPrintfW</b> using four arguments.

The resultant string is "The answer is 1 + 2 = 3." It is contained in the buffer at <i>pszDest</i>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows XP with Service Pack 1 (SP1).

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.h (include Ntstrsafe.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
Unicode and ANSI names

</th>
<td width="70%">
<b>RtlStringCchPrintfW</b> (Unicode) and <b>RtlStringCchPrintfA</b> (ANSI)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlstringcbprintf">RtlStringCbPrintf</a>
</dt>
<dt>
<a href="kernel.rtlstringcchprintfex">RtlStringCchPrintfEx</a>
</dt>
<dt>
<a href="kernel.rtlstringcchvprintf">RtlStringCchVPrintf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchPrintfW function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

