---
UID: NF:wudfwdm.RtlCompareUnicodeString
title: RtlCompareUnicodeString function
author: windows-driver-content
description: The RtlCompareUnicodeString routine compares two Unicode strings.
old-location: kernel\rtlcompareunicodestring.htm
old-project: kernel
ms.assetid: 82567434-be54-4436-a26e-9a89a532addf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlCompareUnicodeString routine [Kernel-Mode Driver Architecture], k109_ddeef320-7510-446b-af6f-756c3999bec1.xml, kernel.rtlcompareunicodestring, RtlCompareUnicodeString, wdm/RtlCompareUnicodeString
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlCompareUnicodeString
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_PERF_STATE_UNIT, PO_FX_PERF_STATE_UNIT"
req.product: Windows 10 or later.
---


# RtlCompareUnicodeString function
The <b>RtlCompareUnicodeString</b> routine compares two Unicode strings.

## Syntax

````
LONG RtlCompareUnicodeString(
  _In_ PCUNICODE_STRING String1,
  _In_ PCUNICODE_STRING String2,
  _In_ BOOLEAN          CaseInSensitive
);
````

## Parameters

`String1`

Pointer to the first string.

`String2`

Pointer to the second string.

`CaseInSensitive`

If <b>TRUE</b>, case should be ignored when doing the comparison.


## Return Value

<b>RtlCompareUnicodeString</b> returns a signed value that gives the results of the comparison:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> equals <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>&lt; Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is less than <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>&gt; Zero </b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is greater than <i>String2</i>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntddk\nf-ntddk-rtlcomparestring.md">RtlCompareString</a>



<a href="..\ntddk\nf-ntddk-rtlequalstring.md">RtlEqualString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCompareUnicodeString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>