---
UID: NF:ntstrsafe.RtlUnalignedStringCchLengthW
title: RtlUnalignedStringCchLengthW function
author: windows-driver-content
description: The RtlUnalignedStringCchLengthW function is a version of the RtlStringCchLength function that accepts an unaligned pointer to a string of Unicode characters.
old-location: kernel\rtlunalignedstringcchlength.htm
old-project: kernel
ms.assetid: 7b9f38f5-7fc9-4670-975d-b7bfeefb2cb8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUnalignedStringCchLengthW
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
req.alt-api: RtlUnalignedStringCchLengthW
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

# RtlUnalignedStringCchLengthW function



## -description
The <b>RtlUnalignedStringCchLengthW</b> function is a version of the <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchlengthw.md">RtlStringCchLength</a> function that accepts an unaligned pointer to a string of Unicode characters.



## -syntax

````
NTSTATUS RtlUnalignedStringCchLengthW(
  _In_      STRSAFE_PCUNZWCH psz,
  _In_      size_t           cchMax,
  _Out_opt_ size_t           *pcchLength
);
````


## -parameters

### -param psz [in]

Supplies a pointer to a buffer that contains a null-terminated string whose length <b>RtlUnalignedStringCchLengthW</b> will check. 


### -param cchMax [in]

Supplies the maximum number of characters that are allowed in the buffer that <i>psz</i> points to, including the terminating NULL character. This value cannot exceed NTSTRSAFE_MAX_CCH. 


### -param pcchLength [out, optional]

Optional. If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the length, in characters, of the string that is contained in the buffer that <i>psz</i> points to. The length does not include the string's terminating NULL character.


## -returns
<b>RtlUnalignedStringCchLengthW</b> returns one of the following NTSTATUS values. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means the string that the <i>psz</i> parameter was not <b>NULL</b>, and the length of the string (including the terminating NULL character) was less than or equal to <i>cchMax</i> characters.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means the value in <i>psz</i> is <b>NULL</b>, <i>cchMax</i> is larger than NTSTRSAFE_MAX_CCH, or <i>psz</i> is longer than <i>cchMax</i>.

 

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.


## -remarks
The <b>RtlUnalignedStringCchLengthW</b> function is available for processor architectures, such as Itanium-based and x64-based, that cause alignment exceptions when software attempts to access unaligned data. On those processors, you can use <b>RtlUnalignedStringCchLengthW</b> instead of <a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchlengthw.md">RtlStringCchLength</a> to avoid alignment exceptions. (For processors that do not cause alignment exceptions, <b>RtlUnalignedStringCchLengthW</b> is equivalent to <b>RtlStringCchLength</b>.)

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
</table>

## -see-also
<dl>
<dt>
<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchlengthw.md">RtlStringCchLength</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnalignedStringCchLengthW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

