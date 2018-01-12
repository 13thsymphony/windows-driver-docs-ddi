---
UID: NF:wdm.RtlIntPtrToUnicodeString
title: RtlIntPtrToUnicodeString macro
author: windows-driver-content
description: The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.
old-location: kernel\rtlintptrtounicodestring.htm
old-project: kernel
ms.assetid: 9bcd278f-b6eb-4e88-8255-f2724bfca285
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntPtrToUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlIntPtrToUnicodeString
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIntPtrToUnicodeString macro



## -description
The <b>RtlIntPtrToUnicodeString</b> routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.



## -syntax

````
NTSTATUS RtlIntPtrToUnicodeString(
  _In_     ULONG_PTR       Value,
  _In_opt_ ULONG           Base,
  _Inout_  PUNICODE_STRING String
);
````


## -parameters

### -param Value [in]

Specifies the ULONG_PTR value to convert. 


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

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i> of <i>String</i> must be large enough to hold the result. 


## -remarks


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
<a href="..\wdm\nf-wdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlintegertounicodestring.md">RtlIntegerToUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlunicodestringtointeger.md">RtlUnicodeStringToInteger</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIntPtrToUnicodeString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

