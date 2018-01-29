---
UID : NF:wdm.RtlIntPtrToUnicodeString
title : RtlIntPtrToUnicodeString macro
author : windows-driver-content
description : The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.
old-location : kernel\rtlintptrtounicodestring.htm
old-project : kernel
ms.assetid : 9bcd278f-b6eb-4e88-8255-f2724bfca285
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlIntPtrToUnicodeString routine [Kernel-Mode Driver Architecture], RtlIntPtrToUnicodeString, wdm/RtlIntPtrToUnicodeString, kernel.rtlintptrtounicodestring, k109_8ec9aafc-288e-4814-a22b-8b8e973689be.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
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
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlIntPtrToUnicodeString function
The <b>RtlIntPtrToUnicodeString</b> routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base.

## Syntax

````
NTSTATUS RtlIntPtrToUnicodeString(
  _In_     ULONG_PTR       Value,
  _In_opt_ ULONG           Base,
  _Inout_  PUNICODE_STRING String
);
````

## Parameters

`Value`

Specifies the ULONG_PTR value to convert.

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

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that receives the string representation of <i>Value</i>. The buffer specified by the <i>Buffer</i> of <i>String</i> must be large enough to hold the result.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-rtlunicodestringtointeger.md">RtlUnicodeStringToInteger</a>

<a href="..\wdm\nf-wdm-rtlintegertounicodestring.md">RtlIntegerToUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIntPtrToUnicodeString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>