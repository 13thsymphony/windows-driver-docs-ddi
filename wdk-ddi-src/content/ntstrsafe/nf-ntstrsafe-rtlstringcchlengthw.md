---
UID: NF:ntstrsafe.RtlStringCchLengthW
title: RtlStringCchLengthW function
author: windows-driver-content
description: The RtlStringCchLengthW and RtlStringCchLengthA functions determine the length, in characters, of a supplied string.
old-location: kernel\rtlstringcchlength.htm
old-project: kernel
ms.assetid: 37d9309d-b105-4e56-b236-530ed49ca116
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlstringcchlength, ntstrsafe/RtlStringCchLengthW, RtlStringCchLengthW function [Kernel-Mode Driver Architecture], RtlStringCchLengthW, ntstrsafe/RtlStringCchLengthA, safestrings_530fb488-be05-467f-a8c5-22016fb49325.xml, RtlStringCchLength, RtlStringCchLengthA
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
req.ddi-compliance: 
req.unicode-ansi: RtlStringCchLengthW (Unicode) and RtlStringCchLengthA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ntstrsafe.lib
-	Ntstrsafe.dll
apiname:
-	RtlStringCchLengthW
-	RtlStringCchLengthA
-	RtlStringCchLengthW
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---


# RtlStringCchLengthW function
The <b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> functions determine the length, in characters, of a supplied string.

## Syntax

````
NTSTATUS RtlStringCchLengthW(
  _In_      LPCTSTR psz,
  _In_      size_t  cchMax,
  _Out_opt_ size_t  *pcch
);
````

## Parameters

`psz`

A pointer to a buffer that contains a null-terminated string, the length of which will be checked.

`cchMax`

The maximum number of characters allowed in the buffer pointed to by <i>psz</i>, including the terminating null character. This value cannot exceed NTSTRSAFE_MAX_CCH.

`pcchLength`

TBD


## Return Value

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.
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
This success status means the string at <i>psz</i> was not <b>NULL</b>, and the length of the string (including the terminating null character) is less than or equal to <i>cchMax</i> characters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This error status means the value in <i>psz</i> is <b>NULL</b>, <i>cchMax</i> is larger than NTSTRSAFE_MAX_CCH, or <i>psz</i> is longer than <i>cchMax</i>.

</td>
</tr>
</table>

## Remarks

<b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> should be used instead of <b>strlen</b>. They are used to ensure that a string is not larger than a given length, in characters. If that condition is met, <b>RtlStringCchLengthW</b> and <b>RtlStringCchLengthA</b> return the current length of the string in characters, not including the terminating null character.

Use <b>RtlStringCchLengthW</b> to handle Unicode strings and <b>RtlStringCchLengthA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.
<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCchLengthW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCchLengthA</b>

</td>
</tr>
</table> 

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows. Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows. |
| **Target Platform** | Desktop |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** | Ntstrsafe.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcblengthw.md">RtlStringCbLength</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCchLengthW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>