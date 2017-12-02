---
UID: NF.wdm.IoCsqInitializeEx
title: IoCsqInitializeEx
author: windows-driver-content
description: The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue.
old-location: kernel\iocsqinitializeex.htm
old-project: kernel
ms.assetid: 9f6501c2-a708-4583-a821-e1b8264ff0af
ms.author: windowsdriverdev
ms.date: 11/28/2017
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
req.iface: 
req.product: Windows 10 or later.
---

# IoCsqInitializeEx function



## -description
<p>The <b>IoCsqInitializeEx</b> routine initializes the dispatch table for a cancel-safe IRP queue.</p>


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
<dl>

### -param Csq [out]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure to be initialized by <b>IoCsqInitializeEx</b>. </p>
</dd>

### -param CsqInsertIrp [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-insert-irp-ex.md">CsqInsertIrpEx</a> function for the driver's cancel-safe IRP queue.</p>
</dd>

### -param CsqRemoveIrp [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-remove-irp.md">CsqRemoveIrp</a> function for the driver's cancel-safe IRP queue.</p>
</dd>

### -param CsqPeekNextIrp [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-peek-next-irp.md">CsqPeekNextIrp</a> function for the driver's cancel-safe IRP queue.</p>
</dd>

### -param CsqAcquireLock [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-acquire-lock.md">CsqAcquireLock</a> function for the driver's cancel-safe IRP queue.</p>
</dd>

### -param CsqReleaseLock [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-release-lock.md">CsqReleaseLock</a> function for the driver's cancel-safe IRP queue.</p>
</dd>

### -param CsqCompleteCanceledIrp [in]

<dd>
<p>Pointer to the driver-defined <a href="..\wdm\nc-wdm-io-csq-complete-canceled-irp.md">CsqCompleteCanceledIrp</a> function for the driver's cancel-safe IRP queue.</p>
</dd>
</dl>

## -returns
<p><b>IoCsqInitializeEx</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.</p>

## -remarks
<p>The <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a> and <b>IoCsqInitializeEx</b> routines initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure that describes a driver's cancel-safe IRP queue. You can use <b>IoCsqInitializeEx</b> to specify an IRP queue with extended capabilities instead of one specified by <b>IoCsqInitialize</b>:</p>

<p>The driver implements a <a href="..\wdm\nc-wdm-io-csq-insert-irp-ex.md">CsqInsertIrpEx</a> routine rather than a <a href="..\wdm\nc-wdm-io-csq-insert-irp.md">CsqInsertIrp</a> routine. <i>CsqInsertIrpEx</i> takes an additional parameter, <i>InsertContext</i>. When the driver calls <a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a> to insert the IRP, it specifies the value that is passed as <i>InsertContext</i>. </p>

<p><b>IoCsqInsertIrpEx</b> returns the return value of <i>CsqInsertIrpEx</i>. Drivers can use the return value to indicate whether an insert operation succeeded or failed.</p>

<p>Otherwise, the effect of <b>IoCsqInitializeEx</b> is identical to that of <b>IoCsqInitialize</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.</p>

<p>Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Server 2003 and later versions of the Windows operating system. The routine is also available in the Csq.lib library that ships with the Windows Driver Kit (WDK) and the Driver Development Kit (DDK) for Windows Server 2003. Drivers that must also work on Windows XP, Windows 2000, and Windows 98/Me can instead link to Csq.lib to use the routine.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
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
<a href="..\wdm\nf-wdm-iocsqinitializeex.md">IoCsqInitializeEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinsertirp.md">IoCsqInsertIrp</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinsertirpex.md">IoCsqInsertIrpEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqremoveirp.md">IoCsqRemoveIrp</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqremovenextirp.md">IoCsqRemoveNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-acquire-lock.md">CsqAcquireLock</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-complete-canceled-irp.md">CsqCompleteCanceledIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-insert-irp.md">CsqInsertIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-insert-irp-ex.md">CsqInsertIrpEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-peek-next-irp.md">CsqPeekNextIrp</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-release-lock.md">CsqReleaseLock</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io-csq-remove-irp.md">CsqRemoveIrp</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqInitializeEx routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
