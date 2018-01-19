---
UID : NF:ntstrsafe.RtlStringCbCopyUnicodeStringEx
title : RtlStringCbCopyUnicodeStringEx function
author : windows-driver-content
description : The RtlStringCbCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location : kernel\rtlstringcbcopyunicodestringex.htm
old-project : kernel
ms.assetid : 146f0e43-a9de-4d4d-8b8f-219c22cfa871
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlStringCbCopyUnicodeStringEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntstrsafe.h
req.include-header : Ntstrsafe.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlStringCbCopyUnicodeStringEx
req.alt-loc : Ntstrsafe.lib,Ntstrsafe.dll
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
req.typenames : "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE"
---


# RtlStringCbCopyUnicodeStringEx function
The <b>RtlStringCbCopyUnicodeStringEx</b> function copies the contents of a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to a specified destination.

## Syntax

````
NTSTATUS RtlStringCbCopyUnicodeStringEx(
  _Out_     NTSTRSAFE_PWSTR  pszDest,
  _In_      size_t           cbDest,
  _In_      PCUNICODE_STRING SourceString,
  _Out_     NTSTRSAFE_PWSTR  *ppszDestEnd,
  _Out_opt_ size_t           *pcbRemaining,
  _In_      DWORD            dwFlags
);
````

## Parameters

`pszDest`

Optional. A pointer to a buffer that receives the copied string. The string that the <i>SourceString</i> parameter's <b>UNICODE_STRING</b> structure points to is copied to the buffer at <i>pszDest</i> and terminated with a null character. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

`cbDest`

The size, in bytes, of the destination buffer. The buffer must be large enough for the string and the terminating null character. The maximum number of bytes in the buffer is NTSTRSAFE_MAX_CCH * sizeof(WCHAR).

`SourceString`

Optional. A pointer to a <b>UNICODE_STRING</b> structure that contains the string to be copied. The maximum number of bytes in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR). This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

`ppszDestEnd`

Optional. If the caller supplies a non-<b>NULL</b> address pointer, then after the copy operation completes, the function loads that address with a pointer to the destination buffer's resulting <b>NULL</b> string terminator.

`pcbRemaining`

Optional. If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer that <i>pszDest</i> points to, including bytes that are used for the terminating null character.

`dwFlags`

One or more flags and, optionally, a fill byte. The flags are defined as follows:


## Return Value

<b>RtlStringCbCopyUnicodeStringEx</b> returns one of the following NTSTATUS values. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means that source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

<b>RtlStringCbCopyUnicodeStringEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

## Remarks

The <b>RtlStringCbCopyUnicodeStringEx</b> function uses the destination buffer's size (which the <i>cbDest</i> parameter specifies) to ensure that the copy operation does not write past the end of the buffer.

<b>RtlStringCbCopyUnicodeStringEx</b> adds to the functionality of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyunicodestring.md">RtlStringCbCopyUnicodeString</a> function by returning a pointer to the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to the function for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString </i>and <i>pszDest</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>pszDest</i> pointer is <b>NULL</b>, the <i>SourceString </i>pointer must be <b>NULL</b> or the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure must describe an empty string.

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

<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcbcopyunicodestring.md">RtlStringCbCopyUnicodeString</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchcopyunicodestringex.md">RtlStringCchCopyUnicodeStringEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCopyUnicodeStringEx function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>