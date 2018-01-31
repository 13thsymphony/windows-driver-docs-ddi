---
UID : NF:wdm.RtlInitUnicodeString
title : RtlInitUnicodeString function
author : windows-driver-content
description : For more information, see the WdmlibRtlInitUnicodeStringEx function.
old-location : kernel\rtlinitunicodestring.htm
old-project : kernel
ms.assetid : c6ef7438-36a6-4da6-b745-2985d9b30614
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : wdm/RtlInitUnicodeString, RtlInitUnicodeString routine [Kernel-Mode Driver Architecture], RtlInitUnicodeString, k109_10e59fa9-6f57-45db-bc11-520660f43b13.xml, kernel.rtlinitunicodestring
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
req.irql : For more information, see  the Remarks section of the WdmlibRtlInitUnicodeStringEx  function.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlInitUnicodeString function
For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.

## Syntax

````
VOID RtlInitUnicodeString(
  _Out_    PUNICODE_STRING DestinationString,
  _In_opt_ PCWSTR          SourceString
);
````

## Parameters

`DestinationString`

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.

`SourceString`

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.


## Return Value

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.

## Remarks

The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="..\wdm\nf-wdm-rtlinitansistring.md">RtlInitAnsiString</a>, <a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>, and <b>RtlInitUnicodeString</b> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | For more information, see  the Remarks section of the WdmlibRtlInitUnicodeStringEx  function. |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a>

<a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinitex.md">RtlUnicodeStringInitEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitUnicodeString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>