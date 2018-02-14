---
UID: NF:wdm.MmPageEntireDriver
title: MmPageEntireDriver function
author: windows-driver-content
description: The MmPageEntireDriver routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.
old-location: kernel\mmpageentiredriver.htm
old-project: kernel
ms.assetid: 467a8e64-c4ed-4bd0-81f8-b792367d33bf
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmPageEntireDriver routine [Kernel-Mode Driver Architecture], kernel.mmpageentiredriver, wdm/MmPageEntireDriver, MmPageEntireDriver, k106_2e2de4d8-8b4f-4f8b-9451-f4f1ea8a5325.xml
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmPageEntireDriver
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmPageEntireDriver function
The <b>MmPageEntireDriver</b> routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.

## Syntax

````
PVOID MmPageEntireDriver(
  _In_ PVOID AddressWithinSection
);
````

## Parameters

`AddressWithinSection`

Pointer to a virtual address within the driver (for example, the address of the <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine).


## Return Value

<b>MmPageEntireDriver</b> returns a pointer to the beginning of the driver image in memory.

## Remarks

Use this routine to force a driver to be completely pageable. Drivers that call <b>MmPageEntireDriver</b> must not have an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine (ISR) registered for any interrupts. If the interrupt occurs while the driver is paged out, the system issues a bug check.

The effect of a call to <b>MmPageEntireDriver</b> can be undone by calling <a href="..\wdm\nf-wdm-mmresetdriverpaging.md">MmResetDriverPaging</a>.

If the driver is already completely pageable, calling <b>MmPageEntireDriver</b> has no effect. For more information about paging an entire driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | IrqlMmApcLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-mmunlockpagableimagesection.md">MmUnlockPagableImageSection</a>



<a href="..\wdm\nf-wdm-mmlockpagabledatasection.md">MmLockPagableDataSection</a>



<a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a>



<a href="..\wdm\nf-wdm-mmresetdriverpaging.md">MmResetDriverPaging</a>



<a href="..\ntddk\nf-ntddk-mmlockpagablesectionbyhandle.md">MmLockPagableSectionByHandle</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmPageEntireDriver routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>