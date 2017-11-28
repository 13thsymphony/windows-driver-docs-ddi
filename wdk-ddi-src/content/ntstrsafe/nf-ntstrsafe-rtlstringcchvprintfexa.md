---
UID: NF.ntstrsafe.RtlStringCchVPrintfExA
title: RtlStringCchVPrintfExA
author: windows-driver-content
description: The RtlStringCchVPrintfExW and RtlStringCchVPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information.
old-location: kernel\rtlstringcchvprintfex.htm
old-project: kernel
ms.assetid: e28dd810-d86f-479f-b049-63a626ed432f
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: RtlStringCchVPrintfExA
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
req.alt-api: RtlStringCchVPrintfEx,RtlStringCchVPrintfExA,RtlStringCchVPrintfExW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchVPrintfExW (Unicode) and RtlStringCchVPrintfExA (ANSI)
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

# RtlStringCchVPrintfExA function



## -description
<p>The <b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> functions create a character-counted text string, with formatting that is based on supplied formatting information.</p>


## -syntax

````
NTSTATUS RtlStringCchVPrintfEx(
  _Out_     LPTSTR  pszDest,
  _In_      size_t  cchDest,
  _Out_opt_ LPTSTR  *ppszDestEnd,
  _Out_opt_ size_t  *pcchRemaining,
  _In_      DWORD   dwFlags,
  _In_opt_  LPCTSTR pszFormat,
  _In_      va_list argList
);
````


## -parameters
<dl>

### -param <i>pszDest</i> [out]

<dd>
<p>A pointer to a caller-supplied buffer that receives a formatted, null-terminated string. The function creates this string from both the formatting string that is supplied by <i>pszFormat</i> and the arguments supplied by <i>argList</i>. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param <i>cchDest</i> [in]

<dd>
<p>The size of the destination buffer, in characters. The buffer must be large enough to contain the formatted string plus the terminating null character. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH. If <i>pszDest</i> is <b>NULL</b>, <i>cchDest</i> must be zero.</p>
</dd>

### -param <i>ppszDestEnd</i> [out, optional]

<dd>
<p>If the caller supplies a non-<b>NULL</b> address pointer then, after the operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator. </p>
</dd>

### -param <i>pcchRemaining</i> [out, optional]

<dd>
<p>If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including those bytes used for the terminating null character.</p>
</dd>

### -param <i>dwFlags</i> [in]

<dd>
<p>One or more flags and, optionally, a fill byte. The flags are defined as follows.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_BEHIND_NULL_"></a><a id="strsafe_fill_behind_null_"></a><dl>

### -param <b>STRSAFE_FILL_BEHIND_NULL </b>

</dl>
</td>
<td width="60%">
<p>If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_IGNORE_NULLS_"></a><a id="strsafe_ignore_nulls_"></a><dl>

### -param <b>STRSAFE_IGNORE_NULLS </b>

</dl>
</td>
<td width="60%">
<p>If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive nonempty strings. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_ON_FAILURE_"></a><a id="strsafe_fill_on_failure_"></a><dl>

### -param <b>STRSAFE_FILL_ON_FAILURE </b>

</dl>
</td>
<td width="60%">
<p>If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NULL_ON_FAILURE_"></a><a id="strsafe_null_on_failure_"></a><dl>

### -param <b>STRSAFE_NULL_ON_FAILURE </b>

</dl>
</td>
<td width="60%">
<p>If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NO_TRUNCATION_"></a><a id="strsafe_no_truncation_"></a><dl>

### -param <b>STRSAFE_NO_TRUNCATION </b>

</dl>
</td>
<td width="60%">
<p>If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>pszFormat</i> [in, optional]

<dd>
<p>Pointer to a null-terminated text string that contains <b>printf</b>-styled formatting directives. The <i>pszFormat</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.</p>
</dd>

### -param <i>argList</i> [in]

<dd>
<p>A <b>va_list</b>-typed argument list. Arguments contained in the argument list will be interpreted by using the formatting string that is supplied by <i>pszFormat</i>.</p>
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
<p><b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> should be used instead of the following functions: </p>

<p><b>vsprintf</b></p>

<p><b>vswprintf</b></p>

<p>_<b>vsnprintf</b></p>

<p>_<b>vsnwprintf</b></p>

<p>All of these functions accept a format string and its arguments, provided as a <b>va_list</b>-typed argument list, and return a formatted string. <b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> receive the size, in characters, of the destination buffer to ensure that they do not write past the end of the buffer.</p>

<p><b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> add to the functionality of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562865">RtlStringCchVPrintf</a> by returning a pointer to the end of the destination string, as well as the number of characters left unused in that string. Flags can be passed to the function for additional control.</p>

<p>For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.</p>

<p>Use <b>RtlStringCchVPrintfExW</b> to handle Unicode strings and <b>RtlStringCchVPrintfExA</b> to handle ANSI strings. The form you use depends on your data.</p>

<p>WCHAR</p>

<p>L"string"</p>

<p><b>RtlStringCchVPrintfExW</b></p>

<p><b>char</b></p>

<p>"string"</p>

<p><b>RtlStringCchVPrintfExA</b></p>

<p> </p>

<p>If  <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings or if any argument strings overlap, the behavior of the function is undefined.</p>

<p>Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszSrc</i> must either be <b>NULL</b> or point to an empty string.</p>

<p>For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.</p>

<p><b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> should be used instead of the following functions: </p>

<p><b>vsprintf</b></p>

<p><b>vswprintf</b></p>

<p>_<b>vsnprintf</b></p>

<p>_<b>vsnwprintf</b></p>

<p>All of these functions accept a format string and its arguments, provided as a <b>va_list</b>-typed argument list, and return a formatted string. <b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> receive the size, in characters, of the destination buffer to ensure that they do not write past the end of the buffer.</p>

<p><b>RtlStringCchVPrintfExW</b> and <b>RtlStringCchVPrintfExA</b> add to the functionality of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562865">RtlStringCchVPrintf</a> by returning a pointer to the end of the destination string, as well as the number of characters left unused in that string. Flags can be passed to the function for additional control.</p>

<p>For more information about <b>va_list</b>-typed argument lists, see the Microsoft Windows SDK documentation.</p>

<p>Use <b>RtlStringCchVPrintfExW</b> to handle Unicode strings and <b>RtlStringCchVPrintfExA</b> to handle ANSI strings. The form you use depends on your data.</p>

<p>WCHAR</p>

<p>L"string"</p>

<p><b>RtlStringCchVPrintfExW</b></p>

<p><b>char</b></p>

<p>"string"</p>

<p><b>RtlStringCchVPrintfExA</b></p>

<p> </p>

<p>If  <i>pszDest</i> and <i>pszFormat</i> point to overlapping strings or if any argument strings overlap, the behavior of the function is undefined.</p>

<p>Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszSrc</i> must either be <b>NULL</b> or point to an empty string.</p>

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
<p>Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.</p>
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
<p><b>RtlStringCchVPrintfExW</b> (Unicode) and <b>RtlStringCchVPrintfExA</b> (ANSI)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562832">RtlStringCbVPrintfEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562864">RtlStringCchPrintfEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562865">RtlStringCchVPrintf</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchVPrintfEx function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
