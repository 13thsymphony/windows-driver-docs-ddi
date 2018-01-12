---
UID: NF:ntstrsafe.RtlStringCbCatExW
title: RtlStringCbCatExW function
author: windows-driver-content
description: The RtlStringCbCatExW and RtlStringCbCatExA functions concatenate two byte-counted strings.
old-location: kernel\rtlstringcbcatex.htm
old-project: kernel
ms.assetid: 9105d6b5-bee3-4fcd-b548-4d403731654d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbCatExW
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
req.alt-api: RtlStringCbCatExW,RtlStringCbCatExA,RtlStringCbCatExW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCatExW (Unicode) and RtlStringCbCatExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlStringCbCatExW function



## -description
The <b>RtlStringCbCatExW</b> and <b>RtlStringCbCatExA</b> functions concatenate two byte-counted strings. 



## -syntax

````
NTSTATUS RtlStringCbCatExW(
  _Inout_opt_ LPTSTR  pszDest,
  _In_        size_t  cbDest,
  _In_opt_    LPCTSTR pszSrc,
  _Out_opt_   LPTSTR  *ppszDestEnd,
  _Out_opt_   size_t  *pcbRemaining,
  _In_        DWORD   dwFlags
);
````


## -parameters

### -param pszDest [in, out, optional]

A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i> is added to the end of the string at <i>pszDest</i> and terminated with a null character. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cbDest [in]

The size of the destination buffer, in bytes. The buffer must be large enough to include both strings and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char).


### -param pszSrc [in, optional]

A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>. The <i>pszSrc</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param ppszDestEnd [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, then after the concatenation operation completes, the function loads that address with a pointer to the destination buffer's resulting <b>NULL</b> string terminator. 


### -param pcbRemaining [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including bytes used for the terminating null character.


### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param STRSAFE_FILL_BEHIND_NULL 

</td>
<td width="60%">
If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. 

</td>
</tr>
<tr>

### -param STRSAFE_IGNORE_NULLS 

</td>
<td width="60%">
If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive nonempty strings. 

</td>
</tr>
<tr>

### -param STRSAFE_FILL_ON_FAILURE 

</td>
<td width="60%">
If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>

### -param STRSAFE_NULL_ON_FAILURE 

</td>
<td width="60%">
If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>

### -param STRSAFE_NO_TRUNCATION 

</td>
<td width="60%">
If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.

</td>
</tr>
</table>
 


## -returns
The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, the strings were fully concatenated without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the concatenated string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER when:

 


## -remarks
<b>RtlStringCbCatExW</b> and <b>RtlStringCbCatExA</b> should be used instead of the following functions: 

<b>strcat</b>

<b>wcscat</b>

Because <b>RtlStringCbCatExW</b> and <b>RtlStringCbCatExA </b>receive the size of the destination buffer as input, they will not write past the end of the buffer. 

<b>RtlStringCbCatEx</b> adds to the functionality of <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatw.md">RtlStringCbCat</a> by returning a pointer to the end of the destination string, as well as the number of bytes left unused in that string. Flags can also be passed to the function for additional control.

Use <b>RtlStringCbCatExW</b> to handle Unicode strings and <b>RtlStringCbCatExA</b> to handle ANSI strings. The form to use is determined by your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCbCatExW</b>

<b>char</b>

"string"

<b>RtlStringCbCatExA</b>

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszSrc</i> must either be <b>NULL</b> or point to an empty string.

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
Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.

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
<b>RtlStringCbCatExW</b> (Unicode) and <b>RtlStringCbCatExA</b> (ANSI)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatw.md">RtlStringCbCat</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcatexw.md">RtlStringCchCatEx</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcatnexw.md">RtlStringCbCatNEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCatExW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

