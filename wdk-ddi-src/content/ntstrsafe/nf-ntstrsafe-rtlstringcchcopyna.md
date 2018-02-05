---
UID : NF:ntstrsafe.RtlStringCchCopyNA
title : RtlStringCchCopyNA function
author : windows-driver-content
description : The RtlStringCchCopyNW and RtlStringCchCopyNA functions copy a character-counted string to a buffer while limiting the size of the copied string.
old-location : kernel\rtlstringcchcopyn.htm
old-project : kernel
ms.assetid : 86ec1a98-d70f-437c-9c8b-005bf78375ba
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlStringCchCopyNW, kernel.rtlstringcchcopyn, RtlStringCchCopyNA, safestrings_6ecbc673-80c3-4568-a6e3-96865035bfed.xml, RtlStringCchCopyNW function [Kernel-Mode Driver Architecture], ntstrsafe/RtlStringCchCopyNW, RtlStringCchCopyN
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
req.ddi-compliance : 
req.unicode-ansi : RtlStringCchCopyNW (Unicode) and RtlStringCchCopyNW (ANSI)
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ntstrsafe.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---


# RtlStringCchCopyNA function
The <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> functions copy a character-counted string to a buffer while limiting the size of the copied string.

## Syntax

````
NTSTATUS RtlStringCchCopyNW(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cchDest,
  _In_  LPCTSTR pszSrc,
  _In_  size_t  cchSrc
);
````

## Parameters

`pszDest`

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i>, up to <i>cchSrc</i> characters, is copied to the buffer at <i>pszDest</i> and terminated with a null character.

`cchDest`

The size of the destination buffer, in characters. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.

`pszSrc`

A pointer to a caller-supplied, null-terminated string.

`cchToCopy`

TBD


## Return Value

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the copied string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

<ul>
<li>The value in <i>cchDest</i>  is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer's length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>

## Remarks

<b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> should be used instead of <b>strncpy</b>. 

The functions copy a given number of characters from a source string. <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b> receive the size, in characters, of the destination buffer to ensure that the functions do not write past the end of the buffer.

Note that these functions behave differently from <b>strncpy</b> in one respect. If <i>cchSrc</i> is larger than the number of characters in <i>pszSrc</i>, <b>RtlStringCchCopyNW</b> and <b>RtlStringCchCopyNA</b>—unlike <b>strncpy</b>—do not continue to pad <i>pszDest</i> with null characters until <i>cchSrc</i> characters have been copied.

Use <b>RtlStringCchCopyNW</b> to handle Unicode strings and <b>RtlStringCchCopyNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.
<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCchCopyNW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCchCopyNA</b>

</td>
</tr>
</table> 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynexw.md">RtlStringCchCopyNEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows. Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows. |
| **Target Platform** | Desktop |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** | Ntstrsafe.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynw.md">RtlStringCbCopyN</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynexw.md">RtlStringCchCopyNEx</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyw.md">RtlStringCchCopy</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchCopyNW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>