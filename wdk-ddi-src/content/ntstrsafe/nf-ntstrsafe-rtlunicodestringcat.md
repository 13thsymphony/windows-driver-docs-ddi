---
UID: NF:ntstrsafe.RtlUnicodeStringCat
title: RtlUnicodeStringCat function
author: windows-driver-content
description: The RtlUnicodeStringCat function concatenates two strings that are contained in UNICODE_STRING structures.
old-location: kernel\rtlunicodestringcat.htm
old-project: kernel
ms.assetid: 15b9ff74-5ca7-4459-af02-b6dc7cd201bf
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUnicodeStringCat
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
req.alt-api: RtlUnicodeStringCat
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
req.typenames: *PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE
---

# RtlUnicodeStringCat function



## -description
The <b>RtlUnicodeStringCat</b> function concatenates two strings that are contained in <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structures.



## -syntax

````
NTSTATUS RtlUnicodeStringCat(
  _Inout_ PUNICODE_STRING  DestinationString,
  _In_    PCUNICODE_STRING SourceString
);
````


## -parameters

### -param DestinationString [in, out]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that, on input, contains a destination string to which the source string will be concatenated. On output, this buffer is the destination buffer that contains the entire resultant string. The source string is added to the end of the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


### -param SourceString [in]

A pointer to a <b>UNICODE_STRING</b> structure. This structure includes a buffer that contains the source string. This string will be added to the end of the destination string. The maximum number of bytes in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR).


## -returns
<b>RtlUnicodeStringCat</b> returns one of the following NTSTATUS values. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means that source data was present, the strings were concatenated without truncation, and the resultant destination buffer is null-terminated.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>This <i>warning</i> status means that the concatenation operation did not complete because of insufficient buffer space. The destination buffer contains a truncated, null-terminated version of the intended result.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

<b>RtlUnicodeStringCat</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.


## -remarks
The <b>RtlUnicodeStringCat</b> function uses the destination buffer's size to ensure that the concatenation operation does not write past the end of the buffer. The function does <u>not</u> terminate the resultant string with a null character value (that is, with zero).

If the source and destination strings overlap, the behavior of the function is undefined.

The <i>SourceString</i> and <i>DestinationString</i> pointers cannot be <b>NULL</b>. If you need to handle <b>NULL</b> pointer values, use <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcatex.md">RtlUnicodeStringCatEx</a>.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringcatex.md">RtlUnicodeStringCatEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringCat function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

