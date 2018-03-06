---
UID: NF:wdm.KeEnterCriticalRegion
title: KeEnterCriticalRegion function
author: windows-driver-content
description: The KeEnterCriticalRegion routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running.
old-location: kernel\keentercriticalregion.htm
old-project: kernel
ms.assetid: 87826cc7-2710-4582-a324-365dd34e2d0d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeEnterCriticalRegion, KeEnterCriticalRegion routine [Kernel-Mode Driver Architecture], k105_cfa63781-e7c6-455a-8e99-4b20872a0b3f.xml, kernel.keentercriticalregion, wdm/KeEnterCriticalRegion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CriticalRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeEnterCriticalRegion
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeEnterCriticalRegion function
The <b>KeEnterCriticalRegion</b> routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running.

## Syntax

````
VOID KeEnterCriticalRegion(void);
````

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

A driver calls this routine to enter a critical region in which the execution of normal kernel APCs is deferred until this driver exits the critical region by calling the <a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a> routine. Any caller of <b>KeEnterCriticalRegion</b> should call <b>KeLeaveCriticalRegion</b> as quickly as possible after entering a critical region.

Highest-level drivers can call <b>KeEnterCriticalRegion</b> while running in the context of the thread that requested the current I/O operation.

A thread that is inside a critical region has both user APCs and normal kernel APCs disabled, but not special kernel APCs. For more information about these APC types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564853">Types of APCs</a>.

Critical regions can be entered recursively and each call to <b>KeEnterCriticalRegion</b> must have a matching call to <b>KeLeaveCriticalRegion</b>.

A driver can use a critical region to acquire and release exclusive access to a shared resource. In this case, the <a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn308551">ExReleaseResourceAndLeaveCriticalRegion</a> routines can be used instead of the <b>KeEnterCriticalRegion</b> and <b>KeLeaveCriticalRegion</b> routines. For more information, see the code example in <a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a>.

For more information about APCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540625">Asynchronous Procedure Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | CriticalRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn308551">ExReleaseResourceAndLeaveCriticalRegion</a>



<a href="..\ntddk\nf-ntddk-keleavecriticalregion.md">KeLeaveCriticalRegion</a>



<a href="..\ntddk\nf-ntddk-keareapcsdisabled.md">KeAreApcsDisabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeEnterCriticalRegion routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>