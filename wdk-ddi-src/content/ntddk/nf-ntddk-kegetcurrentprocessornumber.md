---
UID : NF:ntddk.KeGetCurrentProcessorNumber
title : KeGetCurrentProcessorNumber function
author : windows-driver-content
description : The KeGetCurrentProcessorNumber routine returns the system-assigned number of the current processor on which the caller is running.
old-location : kernel\kegetcurrentprocessornumber.htm
old-project : kernel
ms.assetid : 24de4374-fa73-4891-b212-6f5c7ed53407
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : KeGetCurrentProcessorNumber, KeGetCurrentProcessorNumber routine [Kernel-Mode Driver Architecture], kernel.kegetcurrentprocessornumber, ntddk/KeGetCurrentProcessorNumber, k105_3faba96b-e6d9-40d2-a543-6ea95ce67c73.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeGetCurrentProcessorNumber function
The <b>KeGetCurrentProcessorNumber</b> routine returns the system-assigned number of the current processor on which the caller is running.

## Syntax

````
ULONG KeGetCurrentProcessorNumber(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeGetCurrentProcessorNumber</b> returns a ULONG value that represents the processor on which the caller is currently running.

## Remarks

<b>KeGetCurrentProcessorNumber</b> can be called to debug spin lock usage on SMP machines during driver development. A driver also might call <b>KeGetCurrentProcessorNumber</b> if it maintained some per-processor data and attempted to reduce cache-line contention.

The number of processors in an SMP machine is a zero-based value.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="..\wdm\nf-wdm-kegetcurrentprocessornumberex.md">KeGetCurrentProcessorNumberEx</a> routine, which specifies a processor group, instead of <b>KeGetCurrentProcessorNumber</b>, which does not. However, the implementation of <b>KeGetCurrentProcessorNumber</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows. In this implementation, <b>KeGetCurrentProcessorNumber</b> returns the group-relative processor number if the caller is running on a processor in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support processor groups. If the caller is running on a processor in any group other than group 0, this routine returns a number that is less than the number of processors in group 0. This behavior ensures that the return value is less than the return value of the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a> routine.

If the call to <b>KeGetCurrentProcessorNumber</b> occurs at IRQL &lt;= APC_LEVEL, a processor switch can occur between instructions. Consequently, callers of <b>KeGetCurrentProcessorNumber</b> usually run at IRQL &gt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\wdm\nf-wdm-kegetcurrentprocessornumberex.md">KeGetCurrentProcessorNumberEx</a>

<a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetCurrentProcessorNumber routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>