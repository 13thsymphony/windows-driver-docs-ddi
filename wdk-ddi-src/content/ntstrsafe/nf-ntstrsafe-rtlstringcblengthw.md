---
UID: NF:ntstrsafe.RtlStringCbLengthW
title: RtlStringCbLengthW function
author: windows-driver-content
description: The RtlStringCbLengthW and RtlStringCbLengthA functions determine the length, in bytes, of a supplied string.
old-location: kernel\rtlstringcblength.htm
old-project: kernel
ms.assetid: 74644211-7cf5-48d4-9025-7831cb449979
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlStringCbLength, RtlStringCbLengthW, ntstrsafe/RtlStringCbLengthW, kernel.rtlstringcblength, RtlStringCbLengthA, ntstrsafe/RtlStringCbLengthA, safestrings_1453b6f9-2e9d-4864-96e8-e0245a1a7827.xml, RtlStringCbLengthW function [Kernel-Mode Driver Architecture]
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
req.unicode-ansi: RtlStringCbLengthW (Unicode) and RtlStringCbLengthA (ANSI)
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
-	RtlStringCbLengthW
-	RtlStringCbLengthA
-	RtlStringCbLengthW
product: Windows
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
---


# RtlStringCbLengthW function
The <b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> functions determine the length, in bytes, of a supplied string.

## Syntax

````
NTSTATUS RtlStringCbLengthW(
  _In_      LPCTSTR psz,
  _In_      size_t  cbMax,
  _Out_opt_ size_t  *pcb
);
````

## Parameters

`psz`

A pointer to a buffer that contains a null-terminated string, the length of which will be checked.

`cbMax`

The maximum number of bytes allowed in the buffer that is pointed to by <i>psz</i>, including the terminating null character. 

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char).

`pcbLength`

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
This <i>success</i> status means the string at <i>psz</i> was not <b>NULL</b>, and the length of the string (including the terminating null character) is less than or equal to <i>cbMax</i> characters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the value in <i>psz</i> is <b>NULL</b>, <i>cbMax</i> is larger than NTSTRSAFE_MAX_CCH * sizeof(TCHAR), or <i>psz</i> is longer than <i>cbMax</i>.

</td>
</tr>
</table>

## Remarks

<b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> should be used instead of <b>strlen</b>. Use these functions to ensure that a string is not larger than a given length, in bytes. If that condition is met, <b>RtlStringCbLengthW</b> and <b>RtlStringCbLengthA</b> return the current length of the string in bytes, not including those bytes used for the terminating null character.

Use <b>RtlStringCbLengthW</b> to handle Unicode strings and <b>RtlStringCbLengthA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

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
<b>RtlStringCbLengthW</b>

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
<b>RtlStringCbLengthA</b>

</td>
</tr>
</table>
 

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | ntstrsafe.h (include Ntstrsafe.h) |
| **Library** | Ntstrsafe.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlstringcchlengthw.md">RtlStringCchLength</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbLengthW function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>