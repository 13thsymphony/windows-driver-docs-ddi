---
UID: NF:wdm.RtlIntegerToUnicodeString
title: RtlIntegerToUnicodeString function
author: windows-driver-content
description: The RtlIntegerToUnicodeString routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base.
old-location: kernel\rtlintegertounicodestring.htm
old-project: kernel
ms.assetid: d9c82a97-a8fb-4c23-aa9c-23711d98fd8b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/RtlIntegerToUnicodeString, RtlIntegerToUnicodeString, k109_2ed50455-f426-4072-be25-cab15c4c79cc.xml, kernel.rtlintegertounicodestring, RtlIntegerToUnicodeString routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlIntegerToUnicodeString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlIntegerToUnicodeString function
The <b>RtlIntegerToUnicodeString</b> routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base.

## Syntax

````
NTSTATUS RtlIntegerToUnicodeString(
  _In_     ULONG           Value,
  _In_opt_ ULONG           Base,
  _Inout_  PUNICODE_STRING String
);
````

## Parameters

`Value`

Specifies the ULONG value to convert.

`Base`

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

`String`

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i>  of <i>String</i> must be large enough to hold the result.


## Return Value

<b>RtlIntegerToUnicodeString</b> returns an NTSTATUS value. Possible return values include:

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
The routine successfully converted <i>Value</i> to a Unicode string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
<i>Value</i> is too large to convert, or the <b>UNICODE_STRING</b> structure is too small to hold the result.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified code base is not valid. The only valid values are 0, 2, 8, 10, and 16.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtointeger.md">RtlUnicodeStringToInteger</a>



<a href="..\wdm\nf-wdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIntegerToUnicodeString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>