---
UID: NF:ntstrsafe.RtlStringCchCatW
title: RtlStringCchCatW function
author: windows-driver-content
description: The RtlStringCchCatW and RtlStringCchCatA functions concatenate two character-counted strings.
old-location: kernel\rtlstringcchcat.htm
old-project: kernel
ms.assetid: 4d2d0c14-a311-4235-9ceb-4b703ef602fe
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlStringCchCat, RtlStringCchCatA, RtlStringCchCatW, RtlStringCchCatW function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcat, ntstrsafe/RtlStringCchCatA, ntstrsafe/RtlStringCchCatW, safestrings_03a0e306-3b4e-4808-b257-a8327b688a08.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchCatW (Unicode) and RtlStringCchCatA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
api_name:
-	RtlStringCchCatW
-	RtlStringCchCatA
-	RtlStringCchCatW
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---


# RtlStringCchCatW function
The <b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> functions concatenate two character-counted strings.

## Syntax

```
NTSTRSAFEDDI RtlStringCchCatW(
  NTSTRSAFE_PWSTR  pszDest,
  size_t           cchDest,
  NTSTRSAFE_PCWSTR pszSrc
);
```

## Parameters

`pszDest`

A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i> is added to the end of the string at <i>pszDest</i> and terminated with a null character.

`cchDest`

The size, in characters, of the destination buffer. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH.

`pszSrc`

A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>.


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
This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated, null-terminated version of the intended result.

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
<li>The value in <i>cchDest </i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present.</li>
<li>The destination buffer pointer was <b>NULL</b>, but the buffer size was not zero.</li>
<li>The destination buffer length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>

## Remarks

<b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strcat</b>

</li>
<li>
<b>wcscat</b>

</li>
</ul>
The size, in characters, of the destination buffer is provided to ensure that <b>RtlStringCchCatW</b> and <b>RtlStringCchCatA</b> do not write past the end of the buffer.

Use <b>RtlStringCchCatW</b> to handle Unicode strings and <b>RtlStringCchCatA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCchCatW</b>

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
<b>RtlStringCchCatA</b>

</td>
</tr>
</table>
 

If  <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562835">RtlStringCchCatEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** | Ntstrsafe.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562795">RtlStringCbCat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562835">RtlStringCchCatEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562836">RtlStringCchCatN</a>