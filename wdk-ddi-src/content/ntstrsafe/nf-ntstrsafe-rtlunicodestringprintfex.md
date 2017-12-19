---
UID: NF.ntstrsafe.RtlUnicodeStringPrintfEx
title: RtlUnicodeStringPrintfEx function
author: windows-driver-content
description: The RtlUnicodeStringPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringprintfex.htm
old-project: kernel
ms.assetid: 8a08cb8d-d933-4dc6-8bf2-8f435ffc9eb1
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlUnicodeStringPrintfEx
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
req.alt-api: RtlUnicodeStringPrintfEx
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
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
---

# RtlUnicodeStringPrintfEx function



## -description
The <b>RtlUnicodeStringPrintfEx</b> function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a <a href="kernel.unicode_string">UNICODE_STRING</a> structure.



## -syntax

````
NTSTATUS RtlUnicodeStringPrintfEx(
  _Out_     PUNICODE_STRING  DestinationString,
  _Out_opt_ PUNICODE_STRING  RemainingString,
  _In_      DWORD            dwFlags,
  _In_      NTSTRSAFE_PCWSTR pszFormat,
                             ...
);
````


## -parameters

### -param DestinationString [out]

Optional. A pointer to a <b>UNICODE_STRING</b> structure that receives a formatted string. <b>RtlUnicodeStringPrintfEx</b> creates this string from both the formatting string that <i>pszFormat</i> specifies and the function's argument list. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH. <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param RemainingString [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, <b>RtlUnicodeStringPrintfEx</b> sets this structure's <b>Buffer</b> member to the end of the formatted string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:




### -param STRSAFE_FILL_BEHIND

If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.


### -param STRSAFE_IGNORE_NULLS 

If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringPrintfEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.


### -param STRSAFE_FILL_ON_FAILURE 

If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.


### -param STRSAFE_NULL_ON_FAILURE 

If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.


### -param STRSAFE_NO_TRUNCATION 

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.


### -param STRSAFE_ZERO_LENGTH_ON_FAILURE

If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.

</dd>
</dl>

### -param pszFormat [in]

A pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param ... 

Optional. A list of arguments that <b>RtlUnicodeStringPrintfEx</b> interprets, based on formatting directives that the <i>pszFormat</i> string specifies.


## -returns
<b>RtlUnicodeStringPrintfEx</b> returns one of the following NTSTATUS values. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, and the strings were concatenated without truncation.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means that the operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

<b>RtlUnicodeStringPrintfEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.


## -remarks
The <b>RtlUnicodeStringPrintfEx</b> function uses the destination buffer's size to ensure that the string formatting operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

<b>RtlUnicodeStringPrintfEx</b> adds to the functionality of the <a href="kernel.rtlunicodestringprintf">RtlUnicodeStringPrintf</a> function by returning a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to <b>RtlUnicodeStringPrintfEx</b> for additional control.

If the format string and the destination string overlap, the behavior of the function is undefined.

The <i>pszFormat</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>pszFormat</i> pointer must either be <b>NULL</b> or point to an empty string.

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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlunicodestringprintf">RtlUnicodeStringPrintf</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringvprintf">RtlUnicodeStringVPrintf</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringvprintfex">RtlUnicodeStringVPrintfEx</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringPrintfEx function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

