---
UID: NC:wdm.IO_CSQ_RELEASE_LOCK
title: IO_CSQ_RELEASE_LOCK
author: windows-driver-content
description: The CsqReleaseLock routine is used by the system to release the lock that was acquired using CsqAcquireLock.
old-location: kernel\csqreleaselock.htm
old-project: kernel
ms.assetid: 484cbb69-0adc-4d31-94c2-930ae747a431
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.csqreleaselock, CsqReleaseLock routine [Kernel-Mode Driver Architecture], CsqReleaseLock, IO_CSQ_RELEASE_LOCK, IO_CSQ_RELEASE_LOCK, wdm/CsqReleaseLock, DrvrRtns_054ce175-3354-4b0e-9578-19bab44d39ca.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	CsqReleaseLock
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---


# IO_CSQ_RELEASE_LOCK callback function
The <i>CsqReleaseLock</i> routine is used by the system to release the lock that was acquired using <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>.

## Syntax

```
IO_CSQ_RELEASE_LOCK IoCsqReleaseLock;

void IoCsqReleaseLock(
  PIO_CSQ Csq,
  KIRQL Irql
)
{...}
```

## Parameters

`Csq`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.

`Irql`

Specifies an IRQL. This is the value stored by <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a> when the lock was acquired.


## Return Value

None

## Remarks

The driver specifies the <i>CsqReleaseLock</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqReleaseLock</i> parameter of <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> or <a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system calls this function to release a lock that was acquired using <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>.

If the driver uses a spin lock to implement locking for the queue, it must store the current IRQL when it acquires the lock, and provide the stored IRQL when it releases the lock. The <i>CsqAcquireLock</i> routine stores the current IRQL, and the system passes the stored value as the <i>Irql</i> parameter to <i>CsqReleaseLock</i>. Otherwise the driver can ignore the <i>Irql</i> parameter. For information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Drivers can use any locking mechanism to lock the queue, such as mutexes. For more information about mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>. 


#### Examples

To define a <i>CsqReleaseLock</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqReleaseLock</i> callback routine that is named <code>MyCsqReleaseLock</code>, use the IO_CSQ_RELEASE_LOCK type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_CSQ_RELEASE_LOCK MyCsqReleaseLock;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID 
 MyCsqReleaseLock(
    PIO_CSQ  Csq,
    KIRQL  Irql
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_CSQ_RELEASE_LOCK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_RELEASE_LOCK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>



<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>



<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>



<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>



<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>



<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>



<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>



<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>



<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>



<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>



<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_RELEASE_LOCK routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>