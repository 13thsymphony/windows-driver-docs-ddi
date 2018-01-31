---
UID : NF:wdm.RtlAppendUnicodeStringToString
title : RtlAppendUnicodeStringToString function
author : windows-driver-content
description : The RtlAppendUnicodeStringToString routine concatenates two Unicode strings.
old-location : kernel\rtlappendunicodestringtostring.htm
old-project : kernel
ms.assetid : fb076688-ae8e-430b-ac06-dfef7284591d
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k109_4c17620f-086f-4a0d-aa7a-6bc46d0a0f21.xml, wdm/RtlAppendUnicodeStringToString, kernel.rtlappendunicodestringtostring, RtlAppendUnicodeStringToString, RtlAppendUnicodeStringToString routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
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
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
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
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-rtlappendunicodetostring.md">RtlAppendUnicodeToString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlAppendUnicodeStringToString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>