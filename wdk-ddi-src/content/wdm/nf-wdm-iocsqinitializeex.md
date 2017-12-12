---
UID: NF.wdm.IoCsqInitializeEx
title: IoCsqInitializeEx function
author: windows-driver-content
description: The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue.
old-location: kernel\iocsqinitializeex.htm
old-project: kernel
ms.assetid: 9f6501c2-a708-4583-a821-e1b8264ff0af
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoCsqInitializeEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating system. The routine is also available in the Csq.lib library that ships with the Windows Driver Kit (WDK) and the Driver Development Kit (DDK) for Windows Server 2003. Drivers that must also work on Windows XP, Windows 2000, and Windows 98/Me can instead link to Csq.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCsqInitializeEx
req.alt-loc: NtosKrnl.exe
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
req.product: Windows 10 or later.
---

# IoCsqInitializeEx function



## -description
The <b>IoCsqInitializeEx</b> routine initializes the dispatch table for a cancel-safe IRP queue.



## -syntax

````
NTSTATUS IoCsqInitializeEx(
  _Out_ PIO_CSQ                       Csq,
  _In_  PIO_CSQ_INSERT_IRP_EX         CsqInsertIrp,
  _In_  PIO_CSQ_REMOVE_IRP            CsqRemoveIrp,
  _In_  PIO_CSQ_PEEK_NEXT_IRP         CsqPeekNextIrp,
  _In_  PIO_CSQ_ACQUIRE_LOCK          CsqAcquireLock,
  _In_  PIO_CSQ_RELEASE_LOCK          CsqReleaseLock,
  _In_  PIO_CSQ_COMPLETE_CANCELED_IRP CsqCompleteCanceledIrp
);
````


## -parameters

### -param Csq [out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure to be initialized by <b>IoCsqInitializeEx</b>. 


### -param CsqInsertIrp [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a> function for the driver's cancel-safe IRP queue.


### -param CsqRemoveIrp [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_remove_irp.md">CsqRemoveIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqPeekNextIrp [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_peek_next_irp.md">CsqPeekNextIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqAcquireLock [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqReleaseLock [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_release_lock.md">CsqReleaseLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqCompleteCanceledIrp [in]

Pointer to the driver-defined <a href="..\wdm\nc-wdm-io_csq_complete_canceled_irp.md">CsqCompleteCanceledIrp</a> function for the driver's cancel-safe IRP queue.


## -returns
<b>IoCsqInitializeEx</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.


## -remarks
The <a href="kernel.iocsqinitialize">IoCsqInitialize</a> and <b>IoCsqInitializeEx</b> routines initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure that describes a driver's cancel-safe IRP queue. You can use <b>IoCsqInitializeEx</b> to specify an IRP queue with extended capabilities instead of one specified by <b>IoCsqInitialize</b>:

The driver implements a <a href="..\wdm\nc-wdm-io_csq_insert_irp_ex.md">CsqInsertIrpEx</a> routine rather than a <a href="..\wdm\nc-wdm-io_csq_insert_irp.md">CsqInsertIrp</a> routine. <i>CsqInsertIrpEx</i> takes an additional parameter, <i>InsertContext</i>. When the driver calls <a href="kernel.iocsqinsertirpex">IoCsqInsertIrpEx</a> to insert the IRP, it specifies the value that is passed as <i>InsertContext</i>. 

<b>IoCsqInsertIrpEx</b> returns the return value of <i>CsqInsertIrpEx</i>. Drivers can use the return value to indicate whether an insert operation succeeded or failed.

Otherwise, the effect of <b>IoCsqInitializeEx</b> is identical to that of <b>IoCsqInitialize</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Server 2003 and later versions of the Windows operating system. The routine is also available in the Csq.lib library that ships with the Windows Driver Kit (WDK) and the Driver Development Kit (DDK) for Windows Server 2003. Drivers that must also work on Windows XP, Windows 2000, and Windows 98/Me can instead link to Csq.lib to use the routine.

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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>
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
<a href="..\wdm\nc-wdm-io_csq_acquire_lock.md">CsqAcquireLock</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqInitializeEx routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

