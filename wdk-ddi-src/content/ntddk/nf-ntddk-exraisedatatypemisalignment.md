---
UID: NF:ntddk.ExRaiseDatatypeMisalignment
title: ExRaiseDatatypeMisalignment function
author: windows-driver-content
description: The ExRaiseDatatypeMisalignment routine can be used with structured exception handling to throw a driver-determined exception for a misaligned data type that occurs when a driver processes I/O requests.
old-location: kernel\exraisedatatypemisalignment.htm
old-project: kernel
ms.assetid: 5c8bfd13-31e0-461f-93d2-53ce15c53cdb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExRaiseDatatypeMisalignment routine [Kernel-Mode Driver Architecture], kernel.exraisedatatypemisalignment, k102_ff274a50-ae59-4591-9484-6bc068601ee8.xml, ntddk/ExRaiseDatatypeMisalignment, ExRaiseDatatypeMisalignment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExRaiseDatatypeMisalignment
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# ExRaiseDatatypeMisalignment function
The <b>ExRaiseDatatypeMisalignment</b> routine can be used with structured exception handling to throw a driver-determined exception for a misaligned data type that occurs when a driver processes I/O requests.

## Syntax

````
VOID ExRaiseDatatypeMisalignment(void);
````

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

<b>ExRaiseDatatypeMisalignment</b> raises an exception with the exception code set to STATUS_DATATYPE_MISALIGNMENT.

Because <b>ExRaiseDatatypeMisalignment</b> can only be used at IRQL = PASSIVE_LEVEL, only high-level drivers typically use this routine — for example, file system drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |
| **DDI compliance rules** | IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-exraisestatus.md">ExRaiseStatus</a>

<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>

<a href="..\ntddk\nf-ntddk-exraiseaccessviolation.md">ExRaiseAccessViolation</a>

<a href="..\wdm\nf-wdm-kebugcheckex.md">KeBugCheckEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExRaiseDatatypeMisalignment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>