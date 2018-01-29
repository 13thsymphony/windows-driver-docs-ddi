---
UID : NF:wdfinterrupt.WdfInterruptTryToAcquireLock
title : WdfInterruptTryToAcquireLock function
author : windows-driver-content
description : The WdfInterruptTryToAcquireLock method attempts to acquire an interrupt object's passive lock.
old-location : wdf\wdfinterrupttrytoacquirelock.htm
old-project : wdf
ms.assetid : 272165BE-3DF2-410C-B60A-31B48A3F3231
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfInterruptTryToAcquireLock method, wdfinterrupt/WdfInterruptTryToAcquireLock, PFN_WDFINTERRUPTTRYTOACQUIRELOCK, WdfInterruptTryToAcquireLock, wdf.wdfinterrupttrytoacquirelock, kmdf.wdfinterrupttrytoacquirelock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfinterrupt.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.11
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY"
req.product : Windows 10 or later.
---


# WdfInterruptTryToAcquireLock function
<p class="CCE_Message">[Applies to KMDF and UMDF]

 The <b>WdfInterruptTryToAcquireLock</b> method attempts to acquire an interrupt object's passive lock.

## Syntax

````
BOOLEAN WdfInterruptTryToAcquireLock(
  _In_ WDFINTERRUPT Interrupt
);
````

## Parameters

`Interrupt`

A handle to a framework interrupt object.


## Return Value

<b>WdfInterruptTryToAcquireLock</b> returns TRUE if it successfully acquires the interrupt’s lock. Otherwise, the method returns FALSE.

## Remarks

Drivers that use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a> call <b>WdfInterruptTryToAcquireLock</b> to start a code sequence that executes at IRQL = PASSIVE_LEVEL while holding the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

<b>WdfInterruptTryToAcquireLock</b> attempts to acquire the lock and then returns immediately, whether it has acquired the lock or not. If <b>WdfInterruptTryToAcquireLock</b> does successfully acquire the lock, the framework calls <a href="..\wdm\nf-wdm-keentercriticalregion.md">KeEnterCriticalRegion</a> before returning so that normal kernel APCs are disabled.

For passive-level interrupt objects, drivers must call <b>WdfInterruptTryToAcquireLock</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>, when running in an arbitrary thread, such as a <a href="https://msdn.microsoft.com/5C311AF5-A67A-4F97-8605-1DD16C9D7839">queue object callback function</a>. For example, the driver might call <b>WdfInterruptTryToAcquireLock</b> from <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a>.  Doing so avoids the possibility of deadlock, as described in the Remarks section of <b>WdfInterruptAcquireLock</b>.

When running in  a non-arbitrary thread, such as a work item, the driver should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the framework releases the interrupt lock.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfinterrupt.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestrequeue.md">WdfRequestRequeue</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>

<a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>

<a href="..\wdfsync\nf-wdfsync-wdfwaitlockacquire.md">WdfWaitLockAcquire</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptTryToAcquireLock method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>