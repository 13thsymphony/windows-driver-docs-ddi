---
UID: NF:wudfwdm.RtlAppendUnicodeStringToString
title: RtlAppendUnicodeStringToString function
author: windows-driver-content
description: The RtlAppendUnicodeStringToString routine concatenates two Unicode strings.
old-location: kernel\rtlappendunicodestringtostring.htm
old-project: kernel
ms.assetid: fb076688-ae8e-430b-ac06-dfef7284591d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlAppendUnicodeStringToString, RtlAppendUnicodeStringToString routine [Kernel-Mode Driver Architecture], k109_4c17620f-086f-4a0d-aa7a-6bc46d0a0f21.xml, kernel.rtlappendunicodestringtostring, wdm/RtlAppendUnicodeStringToString
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlAppendUnicodeStringToString
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---


# RtlAppendUnicodeStringToString function
The <b>RtlAppendUnicodeStringToString</b> routine concatenates two Unicode strings.

## Syntax

````
NTSTATUS RtlAppendUnicodeStringToString(
  _Inout_ PUNICODE_STRING  Destination,
  _In_    PCUNICODE_STRING Source
);
````

## Parameters

`Destination`

Pointer to a buffered Unicode string.

`Source`

Pointer to the buffered string to be concatenated.


## Return Value

<b>RtlAppendUnicodeStringToString</b> can return one of the following:

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
The source string was successfully appended to the destination counted string. The destination string length is updated to include the appended bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The destination string length is too small to allow the source string to be concatenated. Accordingly, the destination string length is not updated.

</td>
</tr>
</table>

## Remarks

<b>RtlAppendUnicodeStringToString</b> copies bytes from the source up to the length of the destination buffer.

The <i>Destination</i> and <i>Source</i> buffers must be resident if the caller is running at IRQL &gt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\wudfwdm\nf-wudfwdm-rtlappendunicodetostring.md">RtlAppendUnicodeToString</a>