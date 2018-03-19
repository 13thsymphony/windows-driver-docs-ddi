---
UID: NF:ntstrsafe.RtlUnicodeStringVPrintf
title: RtlUnicodeStringVPrintf function
author: windows-driver-content
description: The RtlUnicodeStringVPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvprintf.htm
old-project: kernel
ms.assetid: d8ca2c47-e3b6-4ead-8d8e-2b2a4fe97658
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlUnicodeStringVPrintf, RtlUnicodeStringVPrintf function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringvprintf, ntstrsafe/RtlUnicodeStringVPrintf, safestrings_45fb9433-8fea-42ec-83fc-772e943a3169.xml
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
req.unicode-ansi: 
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
-	RtlUnicodeStringVPrintf
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE_CONTEXT, *PSYSTEM_POWER_STATE_CONTEXT
---


# RtlUnicodeStringVPrintf function
The <b>RtlUnicodeStringVPrintf</b> function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure.

## Syntax

````
NTSTATUS RtlUnicodeStringVPrintf(
  _Out_ PUNICODE_STRING  DestinationString,
  _In_  NTSTRSAFE_PCWSTR pszFormat,
  _In_  va_list          argList
);
````

## Parameters

`DestinationString`

A pointer to a <b>UNICODE_STRING</b> structure that receives a formatted string. <b>RtlUnicodeStringVPrintf</b> creates this string from the formatting string that <i>pszFormat</i> specifies and the function's argument list. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH.

`pszFormat`

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives.

`argList`

A <b>va_list</b>-typed argument list. Arguments in this argument list will be interpreted by using the formatting string that <i>pszFormat</i> specifies.


## Return Value

<b>RtlUnicodeStringVPrintf</b> returns one of the following NTSTATUS values. 

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
This <i>warning</i> status means the copy operation did not complete due to insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

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

</td>
</tr>
</table>
 

<b>RtlUnicodeStringVPrintf</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure that <i>DestinationString</i> points to are invalid.</li>
<li>The destination buffer is already full.</li>
<li>A <b>NULL</b> pointer is present.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>
For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

## Remarks

The <b>RtlUnicodeStringVPrintf</b> function uses the destination buffer's size to ensure that the string formatting operation does not write past the end of the buffer. The function does not terminate the resultant string with a null character.

If the format string and destination string overlap, the behavior of the function is undefined.

The <i>pszFormat</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvprintfex.md">RtlUnicodeStringVPrintfEx</a> function.

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

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringprintfex.md">RtlUnicodeStringPrintfEx</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringvprintfex.md">RtlUnicodeStringVPrintfEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringprintf.md">RtlUnicodeStringPrintf</a>