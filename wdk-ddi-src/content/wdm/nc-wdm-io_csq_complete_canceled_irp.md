---
UID: NC.wdm.IO_CSQ_COMPLETE_CANCELED_IRP
title: IO_CSQ_COMPLETE_CANCELED_IRP
author: windows-driver-content
description: The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP.
old-location: kernel\csqcompletecanceledirp.htm
old-project: kernel
ms.assetid: ed2f8529-dfc7-4db5-b90c-c0bf8840dc70
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: CsqCompleteCanceledIrp
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# IO_CSQ_COMPLETE_CANCELED_IRP callback



## -description
The <i>CsqCompleteCanceledIrp</i> routine is used by the system to signal to the driver that it can complete a canceled IRP.


## -prototype

````
IO_CSQ_COMPLETE_CANCELED_IRP CsqCompleteCanceledIrp;

VOID CsqCompleteCanceledIrp(
  _In_ PIO_CSQ Csq,
  _In_ PIRP    Irp
)
{ ... }
````


## -parameters

### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.

### -param Irp [in]

Pointer to the IRP to be canceled.

## -returns
None

## -remarks
The driver specifies the <i>CsqCompleteCanceledIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqCompleteCanceledIrp</i> parameter of <a href="kernel.iocsqinitialize">IoCsqInitialize</a> or <a href="kernel.iocsqinitializeex">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The system calls this routine to complete a canceled IRP that has been removed from the driver's queue. Normally, drivers just call <a href="kernel.iocompleterequest">IoCompleteRequest</a> for the IRP with a status of STATUS_CANCELLED.

Drivers are not required to remove the IRP from the queue before completing it as canceled: the system always calls the queue's <a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a> routine to remove the IRP from the queue before calling <i>CsqCompleteCanceledIrp</i>. 

To define a <i>CsqCompleteCanceledIrp</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqCompleteCanceledIrp</i> callback routine that is named <code>MyCsqCompleteCanceledIrp</code>, use the IO_CSQ_COMPLETE_CANCELED_IRP type as shown in this code example:

Then, implement your callback routine as follows:

The IO_CSQ_COMPLETE_CANCELED_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_COMPLETE_CANCELED_IRP function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>
</dt>
<dt>
<a href="kernel.iocompleterequest">IoCompleteRequest</a>
</dt>
<dt>
<a href="kernel.iocsqinitialize">IoCsqInitialize</a>
</dt>
<dt>
<a href="kernel.iocsqinitializeex">IoCsqInitializeEx</a>
</dt>
<dt>
<a href="kernel.iocsqinsertirp">IoCsqInsertIrp</a>
</dt>
<dt>
<a href="kernel.iocsqinsertirpex">IoCsqInsertIrpEx</a>
</dt>
<dt>
<a href="kernel.iocsqremoveirp">IoCsqRemoveIrp</a>
</dt>
<dt>
<a href="kernel.iocsqremovenextirp">IoCsqRemoveNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_CSQ_COMPLETE_CANCELED_IRP routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
