---
UID : NF:wdm.RtlAnsiStringToUnicodeSize
title : RtlAnsiStringToUnicodeSize macro
author : windows-driver-content
description : The RtlAnsiStringToUnicodeSize routine returns the number of bytes required to hold an ANSI string converted into a Unicode string.
old-location : kernel\rtlansistringtounicodesize.htm
old-project : kernel
ms.assetid : 32687aa7-4e14-40cb-baa3-4a97d834bf86
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k109_90cc45c4-2e5b-4f11-823d-5dbc52017e15.xml, kernel.rtlansistringtounicodesize, RtlAnsiStringToUnicodeSize, wdm/RtlAnsiStringToUnicodeSize, RtlAnsiStringToUnicodeSize routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
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


# RtlAnsiStringToUnicodeSize function
The <b>RtlAnsiStringToUnicodeSize</b> routine returns the number of bytes required to hold an ANSI string converted into a Unicode string.

## Syntax

````
ULONG RtlAnsiStringToUnicodeSize(
  _In_ PANSI_STRING AnsiString
);
````

## Parameters

`STRING`

TBD


## Return Value

None

## Remarks

<div class="alert"><b>Note</b>  Casting the return value of the <b>RtlAnsiStringToUnicodeSize</b> routine to USHORT might cause a loss of data. To avoid potential problems, callers of this routine should test the return value for arithmetic overflow. Note that <b>RtlAnsiStringToUnicodeSize</b> accounts for the trailing <b>NULL</b>.</div><div> </div>Callers of <b>RtlAnsiStringToUnicodeSize</b> must be running at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlxansistringtounicodesize.md">RtlxAnsiStringToUnicodeSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlAnsiStringToUnicodeSize routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>