---
UID: NF:ntstrsafe.RtlStringCchCopyNExA
title: RtlStringCchCopyNExA function
author: windows-driver-content
description: The RtlStringCchCopyNExW and RtlStringCchCopyNExA functions copy a character-counted string to a buffer while limiting the size of the copied string.
old-location: kernel\rtlstringcchcopynex.htm
old-project: kernel
ms.assetid: c53672b7-fbe7-45f7-b3ff-30cfeefa7d52
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCchCopyNExA
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
req.alt-api: RtlStringCchCopyNExW,RtlStringCchCopyNExA,RtlStringCchCopyNExW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchCopyNExW (Unicode) and RtlStringCchCopyNExA (ANSI)
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

# RtlStringCchCopyNExA function



## -description
The <b>RtlStringCchCopyNExW</b> and <b>RtlStringCchCopyNExA</b> functions copy a character-counted string to a buffer while limiting the size of the copied string.



## -syntax

````
NTSTATUS RtlStringCchCopyNExW(
  _Out_opt_ LPTSTR  pszDest,
  _In_      size_t  cchDest ,
  _In_opt_  LPCTSTR pszSrc,
  _In_      size_t  cchSrc,
  _Out_opt_ LPTSTR  *ppszDestEnd,
  _Out_opt_ size_t  *pcchRemaining,
  _In_      DWORD   dwFlags
);
````


## -parameters

### -param pszDest [out, optional]

A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i> is copied to the buffer at <i>pszDest</i> and terminated with a null character. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.


### -param cchDest  [in]

The size, in characters, of the destination buffer. The maximum number of characters allowed is NTSTRSAFE_MAX_CCH. If <i>pszDest</i> is <b>NULL</b>, <i>cchDest</i> must be zero.


### -param pszSrc [in, optional]

A pointer to a caller-supplied, null-terminated string. 


### -param cchSrc [in]

The maximum number of characters to copy from <i>pszSrc</i> to the buffer that is supplied by <i>pszDest</i>.


### -param ppszDestEnd [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer then, after the copy operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator. 


### -param pcchRemaining [out, optional]

If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused characters that are in the buffer pointed to by <i>pszDest</i>, including the terminating null character.


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
</dl>This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the created string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

 


## -remarks
<b>RtlStringCchCopyNExW</b> and <b>RtlStringCchCopyNExA</b> should be used instead of <b>strncpy</b>. 

The functions copy a given number of characters from a source string. The size, in characters, of the destination buffer is provided to <b>RtlStringCchCopyNExW</b> and <b>RtlStringCchCopyNExA</b> to ensure that they do not write past the end of the buffer.

Note that these functions behave differently from <b>strncpy</b> in one respect. If <i>cchSrc</i> is larger than the number of characters in <i>pszSrc</i>, <b>RtlStringCchCopyNExW</b> and <b>RtlStringCchCopyNExA</b>—unlike <b>strncpy</b>—do not continue to pad <i>pszDest</i> with null characters until <i>cchSrc</i> characters have been copied.

<b>RtlStringCchCopyNExW</b> and <b>RtlStringCchCopyNExA</b> add to the functionality of <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynw.md">RtlStringCchCopyN</a> by returning a pointer to the end of the destination string, as well as the number of characters left unused in that string. Flags can be passed to the function for additional control.

Use <b>RtlStringCchCopyNExW</b> to handle Unicode strings and <b>RtlStringCchCopyNExA</b> to handle ANSI strings. The form you  use depends on your data, as shown in the following table.

WCHAR

L"string"

<b>RtlStringCchCopyNExW</b>

<b>char</b>

"string"

<b>RtlStringCchCopyNExA</b>

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
<b>RtlStringCchCopyNExW</b> (Unicode) and <b>RtlStringCchCopyNExA</b> (ANSI)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopynw.md">RtlStringCchCopyN</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopynexw.md">RtlStringCbCopyNEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchCopyNExW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

