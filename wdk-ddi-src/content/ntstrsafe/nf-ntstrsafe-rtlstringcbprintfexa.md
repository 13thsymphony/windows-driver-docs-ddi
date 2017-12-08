---
UID: NF.ntstrsafe.RtlStringCbPrintfExA
title: RtlStringCbPrintfExA
author: windows-driver-content
description: The RtlStringCbPrintfExW and RtlStringCbPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcbprintfex.htm
old-project: kernel
ms.assetid: 514a5b40-c9ba-4ed1-871d-fd6ffde583a6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlStringCbPrintfExA
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
req.alt-api: RtlStringCbPrintfEx,RtlStringCbPrintfExA,RtlStringCbPrintfExW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbPrintfExW (Unicode) and RtlStringCbPrintfExA (ANSI)
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

# RtlStringCbPrintfExA function



## -description
<p>The <b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> functions create a byte-counted text string, with formatting that is based on supplied formatting information.</p>


## -syntax

````
NTSTATUS RtlStringCbPrintfEx(
  _Out_opt_ LPTSTR  pszDest,
  _In_      size_t  cbDest,
  _Out_opt_ LPTSTR  *ppszDestEnd,
  _Out_opt_ size_t  *pcbRemaining,
  _In_      DWORD   dwFlags,
  _In_opt_  LPCTSTR pszFormat,
                    ...
);
````


## -parameters
<dl>

### -param pszDest [out, optional]

<dd>
<p>A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the function's argument list. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param cbDest [in]

<dd>
<p>The size of the destination buffer, in bytes. The buffer must be large enough to contain the formatted string plus the terminating null character. </p>
<p>For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). </p>
<p>For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). </p>
<p>If <i>pszDest</i> is <b>NULL</b>, <i>cbDest</i> must be zero.</p>
</dd>

### -param ppszDestEnd [out, optional]

<dd>
<p>If the caller supplies a non-<b>NULL</b> address pointer then, after the operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator. </p>
</dd>

### -param pcbRemaining [out, optional]

<dd>
<p>If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including bytes used for the terminating null character.</p>
</dd>

### -param dwFlags [in]

<dd>
<p>One or more flags and, optionally, a fill byte. The flags are defined as follows:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_BEHIND_NULL_"></a><a id="strsafe_fill_behind_null_"></a><dl>

### -param STRSAFE_FILL_BEHIND_NULL 

</dl>
</td>
<td width="60%">
<p>If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_IGNORE_NULLS_"></a><a id="strsafe_ignore_nulls_"></a><dl>

### -param STRSAFE_IGNORE_NULLS 

</dl>
</td>
<td width="60%">
<p>If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b><i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b><i>pszDest</i> pointers cannot receive nonempty strings. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_ON_FAILURE_"></a><a id="strsafe_fill_on_failure_"></a><dl>

### -param STRSAFE_FILL_ON_FAILURE 

</dl>
</td>
<td width="60%">
<p>If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NULL_ON_FAILURE_"></a><a id="strsafe_null_on_failure_"></a><dl>

### -param STRSAFE_NULL_ON_FAILURE 

</dl>
</td>
<td width="60%">
<p>If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NO_TRUNCATION_"></a><a id="strsafe_no_truncation_"></a><dl>

### -param STRSAFE_NO_TRUNCATION 

</dl>
</td>
<td width="60%">
<p>If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param pszFormat [in, optional]

<dd>
<p>A pointer to a null-terminated text string that contains <b>printf</b>-styled <a href="http://msdn.microsoft.com/en-us/library/56e442dc.aspx">formatting directives</a>. The <i>pszFormat</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param ... 

<dd>
<p>A list of arguments that are interpreted by the function, based on formatting directives contained in the <i>pszFormat</i> string.</p>
</dd>
</dl>

## -returns
<p>The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>This <i>success</i> status means source data was present, the output string was created without truncation, and the resultant destination buffer is null-terminated.</p><dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><p>This <i>warning</i> status means the operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the created string.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.</p>

<p>The function returns the STATUS_INVALID_PARAMETER value when:</p>

<p> </p>

## -remarks
<p><b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> should be used instead of the following functions: </p>

<p><b>sprintf</b></p>

<p><b>swprintf</b></p>

<p>_<b>snprintf</b></p>

<p>_<b>snwprintf</b></p>

<p>All of these functions accept a format string and a list of arguments, interpret them, and create a formatted string. The size, in bytes, of the destination buffer is provided to <b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> to ensure that they do not write past the end of the buffer.</p>

<p><b>RtlStringCbPrintfExW</b> and <b>RtlStringCbPrintfExA</b> add to the functionality of <a href="kernel.rtlstringcbprintf">RtlStringCbPrintf</a> by returning a pointer to the end of the destination string, as well as the number of bytes left unused in that string. Flags can be passed to the function for additional control.</p>

<p>Use <b>RtlStringCbPrintfExW</b> to handle Unicode strings and <b>RtlStringCbPrintfExA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.</p>

<p>WCHAR</p>

<p>L"string"</p>

<p><b>RtlStringCbPrintfExW</b></p>

<p><b>char</b></p>

<p>"string"</p>

<p><b>RtlStringCbPrintfExA</b></p>

<p>If <i>pszDest</i> and <i>pszFormat </i>point to overlapping strings or if any argument strings overlap, the behavior of the function is undefined.</p>

<p>Neither <i>pszFormat</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszFormat</i> must either be <b>NULL</b> or point to an empty string.</p>

<p>For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. </p>

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
<tr>
<th width="30%">
<p>Unicode and ANSI names</p>
</th>
<td width="70%">
<p><b>RtlStringCbPrintfExW</b> (Unicode) and <b>RtlStringCbPrintfExA</b> (ANSI)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlstringcbvprintfex">RtlStringCbVPrintfEx</a>
</dt>
<dt>
<a href="kernel.rtlstringcchprintf">RtlStringCchPrintf</a>
</dt>
<dt>
<a href="kernel.rtlstringcchprintfex">RtlStringCchPrintfEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbPrintfEx function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
