---
UID: NF:wdm.MmResetDriverPaging
title: MmResetDriverPaging function
author: windows-driver-content
description: The MmResetDriverPaging routine resets the pageable status of a driver's sections to that specified when the driver was compiled.
old-location: kernel\mmresetdriverpaging.htm
old-project: kernel
ms.assetid: 6d1d1f0d-d6da-488d-a120-713b77da86a9
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmResetDriverPaging, MmResetDriverPaging routine [Kernel-Mode Driver Architecture], k106_4b691510-4e1f-4da2-bfba-d008a83ef43e.xml, kernel.mmresetdriverpaging, wdm/MmResetDriverPaging
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmResetDriverPaging
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmResetDriverPaging function
The <b>MmResetDriverPaging</b> routine resets the pageable status of a driver's sections to that specified when the driver was compiled.

## Syntax

```
NTKERNELAPI VOID MmResetDriverPaging(
  PVOID AddressWithinSection
);
```

## Parameters

`AddressWithinSection`

A pointer to a virtual address in the driver (for example, the address of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine).


## Return Value

None

## Remarks

<b>MmResetDriverPaging</b> causes those routines that would not normally be pageable, to be locked into memory. Hence, image sections such as .text and .data will be locked in memory if this routine is called.

A driver that calls this routine must do so before enabling interrupts on its device.

A call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554650">MmPageEntireDriver</a> is not a prerequisite to calling this routine. However, calls to <b>MmResetDriverPaging</b> do nothing if the driver's image-section attributes have never been overridden by a call to <b>MmPageEntireDriver</b>.

For more information about paging an entire driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | IrqlMmApcLte, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554601">MmLockPagableCodeSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554607">MmLockPagableDataSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554610">MmLockPagableSectionByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554650">MmPageEntireDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556377">MmUnlockPagableImageSection</a>