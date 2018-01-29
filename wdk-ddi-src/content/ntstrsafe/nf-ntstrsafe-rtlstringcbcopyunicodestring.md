---
UID : NF:ntstrsafe.RtlStringCbCopyUnicodeString
title : RtlStringCbCopyUnicodeString function
author : windows-driver-content
description : The RtlStringCbCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location : kernel\rtlstringcbcopyunicodestring.htm
old-project : kernel
ms.assetid : 87b123ff-0188-4d45-b455-d1ec9def4d63
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : safestrings_1c916f4b-b084-4587-a867-998b789bd2fa.xml, RtlStringCbCopyUnicodeString function [Kernel-Mode Driver Architecture], kernel.rtlstringcbcopyunicodestring, ntstrsafe/RtlStringCbCopyUnicodeString, RtlStringCbCopyUnicodeString
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntstrsafe.h
req.include-header : Ntstrsafe.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows XP with Service Pack 1 (SP1).
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
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
req.typenames : "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE"
---


# RtlStringCbCopyUnicodeString function
The <b>RtlStringCbCopyUnicodeString</b> function copies the contents of a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to a specified destination.

## Syntax

````
NTSTATUS RtlStringCbCopyUnicodeString(
  _Out_ NTSTRSAFE_PWSTR  pszDest,
  _In_  size_t           cbDest,
  _In_  PCUNICODE_STRING SourceString
);
````

## Parameters

`pszDest`

A pointer to a buffer that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer at <i>pszDest</i> and terminated with a null character.

`cbDest`

The size, in bytes, of the destination buffer that <i>pszDest</i> points to. The buffer must be large enough to contain the string and the terminating null character. The maximum number of bytes in the buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * <b>sizeof</b>(WCHAR).

`SourceString`

A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH * <b>sizeof</b>(WCHAR).


## Return Value

<b>RtlStringCbCopyUnicodeString</b> returns one of the following NTSTATUS values.
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
This <i>success</i> status means that source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means that the copy operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

</td>
</tr>
</table> 

<b>RtlStringCbCopyUnicodeString</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:
<ul>
<li>The contents of the <b>UNICODE_STRING</b> structure are invalid.</li>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer (which <i>pszDest</i> points to) is already full.</li>
<li>A buffer pointer is <b>NULL</b>.</li>
<li>The destination buffer's length is zero, but a nonzero length source string is present.</li>
</ul>For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

## Remarks

The <b>RtlStringCbCopyUnicodeString</b> function uses the destination buffer's size (which the <i>cbDest</i> parameter specifies) to ensure that the copy operation does not write past the end of the buffer.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString </i>and <i>pszDest</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyunicodestringex.md">RtlStringCbCopyUnicodeStringEx</a> function.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyunicodestring.md">RtlStringCchCopyUnicodeString</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyunicodestringex.md">RtlStringCbCopyUnicodeStringEx</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCopyUnicodeString function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>