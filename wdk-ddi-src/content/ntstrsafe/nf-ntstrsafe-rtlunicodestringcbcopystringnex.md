---
UID : NF:ntstrsafe.RtlUnicodeStringCbCopyStringNEx
title : RtlUnicodeStringCbCopyStringNEx function
author : windows-driver-content
description : The RtlUnicodeStringCbCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
old-location : kernel\rtlunicodestringcbcopystringnex.htm
old-project : kernel
ms.assetid : 67c364a7-5cf7-424a-8ba3-ba9a11276f5d
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlUnicodeStringCbCopyStringNEx
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
req.alt-api : RtlUnicodeStringCbCopyStringNEx
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


# RtlUnicodeStringCbCopyStringNEx function
The <b>RtlUnicodeStringCbCopyStringNEx</b> function copies a string into a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure while limiting the size of the copied string.

## Syntax

````
NTSTATUS RtlUnicodeStringCbCopyStringNEx(
  _Out_     PUNICODE_STRING  DestinationString,
  _In_      NTSTRSAFE_PCWSTR pszSrc,
  _In_      size_t           cbToCopy,
  _Out_opt_ PUNICODE_STRING  RemainingString,
  _In_      DWORD            dwFlags
);
````

## Parameters

`DestinationString`

Optional. A pointer to a <b>UNICODE_STRING</b> structure that receives the copied string. The string that the <i>pszSrc </i>parameter points to (excluding the terminating null) is copied into the buffer that the <i>DestinationString</i> parameter's <b>UNICODE_STRING</b> structure points to. The maximum number of bytes in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR). <i>DestinationString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

`pszSrc`

Optional. A pointer to the string to be copied. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

`cbToCopy`

The number of bytes to be copied from the source to the destination.

`RemainingString`

Optional. If the caller supplies a non-<b>NULL</b> pointer to a <b>UNICODE_STRING</b> structure, the function sets this structure's <b>Buffer</b> member to the end of the concatenated string, sets the structure's <b>Length</b> member to zero, and sets the structure's <b>MaximumLength</b> member to the number of bytes that are remaining in the destination buffer. <i>RemainingString</i> can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

`dwFlags`

One or more flags and, optionally, a fill byte. The flags are defined as follows:


## Return Value

<b>RtlUnicodeStringCbCopyStringNEx</b> returns one of the following NTSTATUS values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means source data was present, and the strings were concatenated without truncation.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the copied string.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

<b>RtlUnicodeStringCbCopyStringNEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

## Remarks

The <b>RtlUnicodeStringCbCopyStringNEx</b> function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. By default, the function does <u>not</u> terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

<b>RtlUnicodeStringCbCopyStringNEx</b> adds to the functionality of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopystringn.md">RtlUnicodeStringCbCopyStringN</a> function by returning a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that identifies the end of the destination string and the number of bytes left unused in that string. You can pass flags <b>RtlUnicodeStringCbCopyStringNEx</b> for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>pszSrc</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set in <i>dwFlags</i>. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be <b>NULL</b>. If the <i>DestinationString</i> pointer is <b>NULL</b>, the <i>pszSrc</i> pointer must be <b>NULL</b> or point to an empty string.

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
<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcbcopystringn.md">RtlUnicodeStringCbCopyStringN</a>
</dt>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcchcopystringnex.md">RtlUnicodeStringCchCopyStringNEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCbCopyStringNEx function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>