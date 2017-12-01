---
UID: NF.ntstrsafe.RtlUnicodeStringCbCopyNEx
title: RtlUnicodeStringCbCopyNEx
author: windows-driver-content
description: The RtlUnicodeStringCbCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcbcopynex.htm
old-project: kernel
ms.assetid: 08b2e13c-bbd6-4344-83cb-3bb911c5da70
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlUnicodeStringCbCopyNEx
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
req.alt-api: RtlUnicodeStringCbCopyNEx
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
req.iface: 
---

# RtlUnicodeStringCbCopyNEx function



## -description
<p>The <b>RtlUnicodeStringCbCopyNEx</b> function copies a string from one <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure to another while limiting the size of the copied string.</p>


## -syntax

````
NTSTATUS RtlUnicodeStringCbCopyNEx(
  _Out_     PUNICODE_STRING  DestinationString,
  _In_      PCUNICODE_STRING SourceString,
  _In_      size_t           cbToCopy,
  _Out_opt_ PUNICODE_STRING  RemainingString,
  _In_      DWORD            dwFlags
);
````


## -parameters
<dl>

### -param <i>DestinationString</i> [out]

<dd>
<p>Optional. A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of bytes in the <i>DestinationString </i>structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR). <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param <i>SourceString</i> [in]

<dd>
<p>Optional. A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR). <i>SourceString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param <i>cbToCopy</i> [in]

<dd>
<p>The number of bytes to be copied from the source to the destination. </p>
</dd>

### -param <i>RemainingString</i> [out, optional]

<dd>
<p>Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, the function sets this structure's <b>Buffer</b> member to the end of the concatenated string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param <i>dwFlags</i> [in]

<dd>
<p>One or more flags and, optionally, a fill byte. The flags are defined as follows:</p>
<p></p>
<dl>

### -param <a id="STRSAFE_FILL_BEHIND"></a><a id="strsafe_fill_behind"></a>STRSAFE_FILL_BEHIND

<dd>
<p>If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.</p>
</dd>

### -param <a id="STRSAFE_IGNORE_NULLS_"></a><a id="strsafe_ignore_nulls_"></a>STRSAFE_IGNORE_NULLS 

<dd>
<p>If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringCbCopyNEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.</p>
</dd>

### -param <a id="STRSAFE_FILL_ON_FAILURE_"></a><a id="strsafe_fill_on_failure_"></a>STRSAFE_FILL_ON_FAILURE 

<dd>
<p>If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.</p>
</dd>

### -param <a id="STRSAFE_NULL_ON_FAILURE_"></a><a id="strsafe_null_on_failure_"></a>STRSAFE_NULL_ON_FAILURE 

<dd>
<p>If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.</p>
</dd>

### -param <a id="STRSAFE_NO_TRUNCATION_"></a><a id="strsafe_no_truncation_"></a>STRSAFE_NO_TRUNCATION 

<dd>
<p>If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.</p>
</dd>

### -param <a id="STRSAFE_ZERO_LENGTH_ON_FAILURE"></a><a id="strsafe_zero_length_on_failure"></a>STRSAFE_ZERO_LENGTH_ON_FAILURE

<dd>
<p>If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.</p>
</dd>
</dl>
</dd>
</dl>

## -returns
<p><b>RtlUnicodeStringCbCopyNEx</b> returns one of the following NTSTATUS values. </p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>This <i>success</i> status means source data was present, and the strings were concatenated without truncation.</p><dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><p>This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.</p>

<p> </p>

<p><b>RtlUnicodeStringCbCopyNEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:</p>

<p>For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.</p>

## -remarks
<p>The <b>RtlUnicodeStringCbCopyNEx</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.</p>

<p><b>RtlUnicodeStringCbCopyNEx</b> adds to the functionality of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopyn.md">RtlUnicodeStringCbCopyN</a> function by returning a <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to <b>RtlUnicodeStringCbCopyNEx</b> for additional control.</p>

<p>If the source and destination strings overlap, the behavior of the function is undefined.</p>

<p>The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>SourceString</i> pointer must be <b>NULL</b> or the <b>UNICODE_STRING</b> structure must contain an empty string.</p>

<p>For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows XP with Service Pack 1 (SP1).</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.h (include Ntstrsafe.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopyn.md">RtlUnicodeStringCbCopyN</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopynex.md">RtlUnicodeStringCchCopyNEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCbCopyNEx function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
