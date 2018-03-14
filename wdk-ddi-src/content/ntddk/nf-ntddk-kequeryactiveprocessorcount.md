---
UID: NF:ntddk.KeQueryActiveProcessorCount
title: KeQueryActiveProcessorCount function
author: windows-driver-content
description: The KeQueryActiveProcessorCount routine returns the number of currently active processors.
old-location: kernel\kequeryactiveprocessorcount.htm
old-project: kernel
ms.assetid: 4369ad33-ba4a-45db-9a41-e77d6c55da53
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeQueryActiveProcessorCount, KeQueryActiveProcessorCount routine [Kernel-Mode Driver Architecture], k105_23574ace-ab66-43bb-976f-ca7310cece9a.xml, kernel.kequeryactiveprocessorcount, wdm/KeQueryActiveProcessorCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryActiveProcessorCount
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeQueryActiveProcessorCount function
The <b>KeQueryActiveProcessorCount</b> routine returns the number of currently active processors.

## Syntax

````
ULONG KeQueryActiveProcessorCount(
  _Out_opt_ PKAFFINITY ActiveProcessors
);
````

## Parameters

`ActiveProcessors`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable into which the routine writes a bitmask that represents the set of currently active processors. In a hot-add environment, this mask may change during runtime. This parameter is optional and can be specified as <b>NULL</b> if the caller does not require the mask of active processors.


## Return Value

<b>KeQueryActiveProcessorCount</b> returns the number of currently active processors.

## Remarks

A device driver calls the <b>KeQueryActiveProcessorCount</b> routine to retrieve the number of currently active processors. Device drivers that are built for Windows Vista and later versions of the Windows operating system should not use the <b>KeNumberProcessors</b> kernel variable for this purpose.

Callers cannot assume that the <b>KeQueryActiveProcessorCount</b> routine maps processors to bits in the returned <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value consecutively, or that the routine will return the same bitmask each time it is called.

Callers must also be aware that the value returned by <b>KeQueryActiveProcessorCount</b> can change at runtime on versions of Windows that support hot-add CPU functionality.

If necessary, register for notification of changes to the number of processors by calling the <a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a> routine.

To query just the affinity mask without getting the number of active processors, use <a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a> routine, which specifies a processor group, instead of <b>KeQueryActiveProcessorCount</b>, which does not. However, the implementation of <b>KeQueryActiveProcessorCount</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeQueryActiveProcessorCount</b> returns the number of active logical processors in group 0, and writes an affinity mask to *<i>ActiveProcessors</i> that specifies the set of active logical processors in group 0. 

The KAFFINITY type is an affinity mask that represents a set of logical processors in a group. The KAFFINITY type is 32 bits on a 32-bit version of Windows and is 64 bits on a 64-bit version of Windows.

If a group contains <i>n</i> logical processors, the processors are numbered from 0 to <i>n</i>-1. Processor number <i>i</i> in the group is represented by bit <i>i</i> in the affinity mask, where <i>i</i> is in the range 0 to <i>n</i>-1. Affinity mask bits that do not correspond to logical processors are always zero.

For example, if a KAFFINITY value identifies the active processors in a group, the mask bit for a processor is one if the processor is active, and is zero if the processor is not active.

The number of bits in the affinity mask determines the maximum number of logical processors in a group. For a 64-bit version of Windows, the maximum number of processors per group is 64. For a 32-bit version of Windows, the maximum number of processors per group is 32. Call the <a href="..\wdm\nf-wdm-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a> routine to obtain the maximum number of processors per group. This number depends on the hardware configuration of the multiprocessor system, but can never exceed the fixed 64-processor and 32-processor limits that are set by the 64-bit and 32-bit versions of Windows, respectively.

The <a href="..\minitape\ns-minitape-_group_affinity.md">GROUP_AFFINITY</a> structure contains an affinity mask and a group number. The group number identifies the group to which the affinity mask applies.

Kernel routines that use the KAFFINITY type include <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>, <b>KeQueryActiveProcessorCount</b>, and <a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-kequeryactiveprocessors.md">KeQueryActiveProcessors</a>



<a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a>



<a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryActiveProcessorCount routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>