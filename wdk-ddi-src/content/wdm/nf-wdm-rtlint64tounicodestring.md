---
UID: NF.wdm.RtlInt64ToUnicodeString
title: RtlInt64ToUnicodeString function
author: windows-driver-content
description: The RtlInt64ToUnicodeString routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base.
old-location: kernel\rtlint64tounicodestring.htm
old-project: kernel
ms.assetid: 36f146a7-cdc2-4b88-bd9a-5008bf94c180
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlInt64ToUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInt64ToUnicodeString
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
req.product: Windows 10 or later.
---

# RtlInt64ToUnicodeString function



## -description
The <b>RtlInt64ToUnicodeString</b> routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base.



## -syntax

````
NTSTATUS RtlInt64ToUnicodeString(
  _In_     ULONGLONG       Value,
  _In_opt_ ULONG           Base,
  _Inout_  PUNICODE_STRING String
);
````


## -parameters

### -param Value [in]

Specifies the ULONGLONG value to convert. 


### -param Base [in, optional]

Specifies the base to use when converting <i>Value</i> to a string. The possible values are:

<table>
<tr>
<th>Value</th>
<th>Base</th>
</tr>
<tr>
<td>
16

</td>
<td>
Hexadecimal

</td>
</tr>
<tr>
<td>
8

</td>
<td>
Octal

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Binary

</td>
</tr>
<tr>
<td>
0 or 10

</td>
<td>
Decimal

</td>
</tr>
</table>
 


### -param String [in, out]

Pointer to the <a href="kernel.unicode_string">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i>  of <i>String</i> must be large enough to hold the result. 


## -returns
<b>RtlInt64ToUnicodeString</b> returns an NTSTATUS value. Possible return values include :
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine successfully converted <i>Value</i> to a Unicode string.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><i>Value</i> is too large to convert, or the <b>UNICODE_STRING</b> structure is too small to hold the result.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified code base is not valid. The only valid values are 0, 2, 8, 10, and 16.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="kernel.rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringtointeger">RtlUnicodeStringToInteger</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInt64ToUnicodeString routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

