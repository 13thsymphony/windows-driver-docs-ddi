---
UID : NF:wdm.ExReleaseSpinLockExclusive
title : ExReleaseSpinLockExclusive function
author : windows-driver-content
description : The ExReleaseSpinLockExclusive routine releases a spin lock that the caller previously acquired for exclusive access, and restores the IRQL to its original value.
old-location : kernel\exreleasespinlockexclusive_.htm
old-project : kernel
ms.assetid : D10C65A6-96E7-4BE0-BDD5-EFD129DC424C
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.exreleasespinlockexclusive_, ExReleaseSpinLockExclusive, wdm/ExReleaseSpinLockExclusive, ExReleaseSpinLockExclusive routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows Vista with SP1.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : DISPATCH_LEVEL (See Remarks.)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ExReleaseSpinLockExclusive function
The <b>ExReleaseSpinLockExclusive</b> routine releases a <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">spin lock</a> that the caller previously acquired for exclusive access, and restores the IRQL to its original value.

## Syntax

````
VOID ExReleaseSpinLockExclusive (
  _Inout_ PEX_SPIN_LOCK SpinLock,
  _In_    KIRQL         OldIrql
);
````

## Parameters

``



`OldIrql`

The interrupt request level (IRQL) to restore. Set this parameter to the KIRQL value that was returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451007">ExAcquireSpinLockExclusive</a> call that acquired the spin lock.


## Return Value

None.

## Remarks

This routine must be called only for a spin lock that is owned by the caller.

On entry to this routine, the caller must be running at IRQL = DISPATCH_LEVEL. Before exiting, <b>ExReleaseSpinLockExclusive</b> restores the IRQL to the value specified by the <i>OldIrql</i> parameter.

The caller should hold the spin lock only briefly before releasing it. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL (See Remarks.) |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451007">ExAcquireSpinLockExclusive</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExReleaseSpinLockExclusive  routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>