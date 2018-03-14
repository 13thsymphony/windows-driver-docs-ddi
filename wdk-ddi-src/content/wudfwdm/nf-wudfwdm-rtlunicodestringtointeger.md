---
UID: NF:wudfwdm.RtlUnicodeStringToInteger
title: RtlUnicodeStringToInteger function
author: windows-driver-content
description: The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value.
old-location: kernel\rtlunicodestringtointeger.htm
old-project: kernel
ms.assetid: d9357864-d49b-44fe-b884-64c6da609789
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlUnicodeStringToInteger, RtlUnicodeStringToInteger routine [Kernel-Mode Driver Architecture], k109_862feacf-64af-4aae-87b5-264ef277ea22.xml, kernel.rtlunicodestringtointeger, wdm/RtlUnicodeStringToInteger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlUnicodeStringToInteger
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---


# RtlUnicodeStringToInteger function
The <b>RtlUnicodeStringToInteger</b> routine converts a Unicode string representation of a number to the equivalent integer value.

## Syntax

````
NTSTATUS RtlUnicodeStringToInteger(
  _In_     PCUNICODE_STRING String,
  _In_opt_ ULONG            Base,
  _Out_    PULONG           Value
);
````

## Parameters

`String`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the number representation to convert to the equivalent integer value.

`Base`

A numeric value that indicates the base (or radix) of the number that the Unicode string represents. This parameter value is optional and can be set to zero.

If <i>Base</i> is zero, <b>RtlUnicodeStringToInteger</b> checks the prefix of the Unicode string to determine the base of the number:

<ul>
<li>
If the prefix is "0x", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as a hexadecimal integer.

</li>
<li>
If the prefix is "0o", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as an octal integer.

</li>
<li>
If the prefix is "0b", <b>RtlUnicodeStringToInteger</b> interprets the number in the string as a binary integer.

</li>
</ul>
If the Unicode string does not contain any of these prefixes, <b>RtlUnicodeStringToInteger</b> treats the string as a base-10 integer.

`Value`

A pointer to a ULONG variable to which <b>RtlUnicodeStringToInteger</b> writes the integer value that results from conversion of the Unicode string.


## Return Value

If the conversion is successful, the <b>RtlUnicodeStringToInteger</b> routine returns STATUS_SUCCESS and sets *<i>Value</i> to the integer value represented by the number in the Unicode string. If the string is not empty, but does not start with a valid number representation, the routine returns STATUS_SUCCESS and sets *<i>Value</i> to zero. If the string is empty, the routine fails and returns STATUS_INVALID_PARAMETER.

## Remarks

This routine skips any white space at the start of the input string to find the start of the number.

If the first non-white space character in the string is a hyphen (-), the integer value written to *<i>Value</i> is negative; otherwise, if the first character is a "+" or there is no sign character, the integer value written to *<i>Value</i> is positive.

 If the string does not contain a valid number, or if the first digit in the string is preceded by a non-white space character other than '+' or '-', the routine sets the output value to zero and returns STATUS_SUCCESS.

A substring that contains one or more valid digits is terminated by any character that is not a valid digit. For example, if <i>Base</i> = 2, valid digits are '0' and '1'. If <i>Base</i> = 8, valid digits are '0' to '7'. If <i>Base</i> = 10, valid digits are '0' to '9'. If <i>Base</i> = 16, valid digits are '0' to '9', 'a' to 'f', and 'A' to 'F'.

The following table contains examples of output values that result from various combinations of input strings and <i>Base</i> parameter values.

<table>
<tr>
<th>Input string</th>
<th>Base</th>
<th>Output value</th>
</tr>
<tr>
<td>"123"</td>
<td>10</td>
<td>123</td>
</tr>
<tr>
<td>"  -345"</td>
<td>10</td>
<td>-345</td>
</tr>
<tr>
<td>"xyz"</td>
<td>10</td>
<td>0</td>
</tr>
<tr>
<td>"   +678abc"</td>
<td>10</td>
<td>678</td>
</tr>
<tr>
<td>"   +678abc"</td>
<td>16</td>
<td>6785724</td>
</tr>
<tr>
<td>"007"</td>
<td>10</td>
<td>7</td>
</tr>
<tr>
<td>"789"</td>
<td>8</td>
<td>7</td>
</tr>
<tr>
<td>"FGH"</td>
<td>16</td>
<td>15</td>
</tr>
<tr>
<td>"      "</td>
<td>10</td>
<td>0</td>
</tr>
</table>
 

A related routine, <a href="..\wudfwdm\nf-wudfwdm-rtlintegertounicodestring.md">RtlIntegerToUnicodeString</a>, converts an integer value to the equivalent Unicode string representation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlintegertounicodestring.md">RtlIntegerToUnicodeString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringToInteger routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>