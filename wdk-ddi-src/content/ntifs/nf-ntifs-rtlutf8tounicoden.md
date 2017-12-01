---
UID: NF.ntifs.RtlUTF8ToUnicodeN
title: RtlUTF8ToUnicodeN
author: windows-driver-content
description: The RtlUTF8ToUnicodeN routine converts a UTF-8 string to a Unicode string.
old-location: kernel\rtlutf8tounicoden.htm
old-project: kernel
ms.assetid: 0b5f791a-9814-4058-8ee0-8f113ca3ade2
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlUTF8ToUnicodeN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUTF8ToUnicodeN
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
---

# RtlUTF8ToUnicodeN function



## -description
<p>The <b>RtlUTF8ToUnicodeN</b> routine converts a UTF-8 string to a Unicode string. </p>


## -syntax

````
NTSTATUS RtlUTF8ToUnicodeN(
  _Out_opt_ PWSTR  UnicodeStringDestination,
  _In_      ULONG  UnicodeStringMaxByteCount,
  _Out_     PULONG UnicodeStringActualByteCount,
  _In_      PCCH   UTF8StringSource,
  _In_      ULONG  UTF8StringByteCount
);
````


## -parameters
<dl>

### -param <i>UnicodeStringDestination</i> [out, optional]

<dd>
<p>A pointer to a caller-allocated destination buffer into which the routine writes the Unicode output string. If this parameter is <b>NULL</b>, the routine writes the required size of the output buffer to *<i>UnicodeStringActualByteCount</i>. </p>
</dd>

### -param <i>UnicodeStringMaxByteCount</i> [in]

<dd>
<p>Specifies the maximum number of bytes that the routine can write to the buffer that <i>UnicodeStringDestination</i> points to. If <i>UnicodeStringDestination</i> = <b>NULL</b>, set <i>UnicodeStringMaxByteCount</i> = 0. </p>
</dd>

### -param <i>UnicodeStringActualByteCount</i> [out]

<dd>
<p>A pointer to a location into which the routine writes the actual number of bytes that the routine has written to the buffer that <i>UnicodeStringDestination</i> points to. If <i>UnicodeStringDestination</i> is non-<b>NULL</b>, this count never exceeds the value of <i>UnicodeStringMaxByteCount</i>. If <i>UnicodeStringDestination</i> is <b>NULL</b>, this count is the number of bytes that are required to contain the entire output string. </p>
</dd>

### -param <i>UTF8StringSource</i> [in]

<dd>
<p>A pointer to the UTF-8 source string.</p>
</dd>

### -param <i>UTF8StringByteCount</i> [in]

<dd>
<p>Specifies the number of bytes in the UTF-8 source string that the <i>UTF8StringSource</i> parameter points to. </p>
</dd>
</dl>

## -returns
<p><b>RtlUTF8ToUnicodeN</b> returns STATUS_SUCCESS if the call is successful and all UTF-8 character codes in the input string were converted to the corresponding Unicode character codes in the output string. It returns STATUS_SOME_NOT_MAPPED if the call is successful but one or more input characters were invalid and were converted to the Unicode replacement character, U+FFFD. Possible error return values include the following error codes:</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The <i>UnicodeStringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <i>UnicodeStringDestination</i> and <i>UnicodeStringActualByteCount</i> parameters are both <b>NULL</b>. </p><dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl><p>The <i>UTF8StringSource</i> parameter is <b>NULL</b>. </p>

<p> </p>

## -remarks
<p>The Unicode output string is null-terminated only if the UTF-8 input string is null-terminated.</p>

<p>The routine returns STATUS_BUFFER_TOO_SMALL if the <i>UnicodeStringMaxByteCount</i> parameter specifies a buffer size that is too small to contain the entire output string. In this case, the routine writes as many Unicode characters as will fit in the buffer, and the *<i>UnicodeStringActualByteCount</i> value specifies the number of valid bytes that the routine has written to the buffer. The partial string that is contained in the output buffer might not include a terminating null character.</p>

<p>You can make an initial call to <b>RtlUTF8ToUnicodeN</b> to obtain the required output buffer size, and then call <b>RtlUTF8ToUnicodeN</b> again to obtain the Unicode output string. In the initial call, set <i>UnicodeStringDestination</i> = <b>NULL</b> and <i>UnicodeStringMaxByteCount</i> = 0, and the routine will write the required buffer size to *<i>UnicodeStringActualByteCount</i>. Next, allocate a buffer of the required size and call <b>RtlUTF8ToUnicodeN</b> a second time to obtain the Unicode output string.</p>

<p><b>RtlUTF8ToUnicodeN</b> supports Unicode surrogate pairs. However, a surrogate leading word value that is not followed by a trailing word value, or a trailing word value that is not preceded by a leading word value, is not recognized as a valid character and is replaced by the Unicode replacement character, U+FFFD.</p>

<p><b>RtlUTF8ToUnicodeN</b> continues to convert the input string to an output string until it reaches the end of the source buffer or the end of the destination buffer, whichever occurs first. The routine converts any null characters in the input string to null characters in the output string. If the input string contains a terminating null character, but the null character is not located at the end of the source buffer, the routine continues past the terminating null character until it reaches the end of the available buffer space.</p>

<p>The <a href="..\ntifs\nf-ntifs-rtlunicodetoutf8n.md">RtlUnicodeToUTF8N</a> routine converts a Unicode string to a UTF-8 string.</p>

<p>You can use the <b>RtlUTF8ToUnicode</b> and <b>RtlUnicodeToUTF8N</b> routines to perform a lossless conversion of valid text strings between the UTF-8 and Unicode formats. However, strings that have arbitrary data values are likely to violate the Unicode rules for encoding surrogate pairs, and any information that is contained in the invalid values in an input string is lost and cannot be recovered from the resulting output string. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of Windows. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntifs.h, Wdm.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="..\ntifs\nf-ntifs-rtlunicodetoutf8n.md">RtlUnicodeToUTF8N</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUTF8ToUnicodeN routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
