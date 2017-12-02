---
UID: NF.wdm.IoCsqRemoveNextIrp
title: IoCsqRemoveNextIrp
author: windows-driver-content
description: The IoCsqRemoveNextIrp routine removes the next matching IRP in the queue.
old-location: kernel\iocsqremovenextirp.htm
old-project: kernel
ms.assetid: db92bbc1-7257-4e84-af69-ce09c1fd998e
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IoCsqRemoveNextIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows. Drivers that must also work on Windows 2000 and Windows 98/Me can instead link to Csq.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCsqRemoveNextIrp
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# IoCsqRemoveNextIrp function



## -description
<p>The <b>IoCsqRemoveNextIrp</b> routine removes the next matching IRP in the queue.</p>


## -syntax

````
PIRP IoCsqRemoveNextIrp(
  _Inout_  PIO_CSQ Csq,
  _In_opt_ PVOID   PeekContext
);
````


## -parameters
<dl>

### -param Csq [in, out]

<dd>
<p>Pointer to the driver's dispatch table for cancel-safe IRP queues. The dispatch table must be initialized by <a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>.</p>
</dd>

### -param PeekContext [in, optional]

<dd>
<p>A pointer to a driver-defined context value. <b>IoCsqRemoveNextIrp</b> passes this parameter to the driver's <a href="..\wdm\nc-wdm-io-csq-peek-next-irp.md">CsqPeekNextIrp</a> routine. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -returns
<p>This routine returns a pointer to the next matching IRP in the queue, or <b>NULL</b> if no more IRPs are available. The routine only returns IRPs that have not yet been canceled.</p>

## -remarks
<p><b>IoCsqRemoveNextIrp</b> uses the queue's dispatch routines to remove the IRP. The <b>IoCsqRemoveNextIrp</b> routine:</p>

<p>Calls the queue's <a href="..\wdm\nc-wdm-io-csq-acquire-lock.md">CsqAcquireLock</a> routine to lock the queue.</p>

<p>Calls the queue's <a href="..\wdm\nc-wdm-io-csq-peek-next-irp.md">CsqPeekNextIrp</a> routine to find the next matching IRP in the queue. <b>IoCsqRemoveNextIrp</b> passes the value of the <i>PeekContext</i> parameter as the <i>PeekContext</i> parameter of <i>CsqPeekNextIrp</i>. <i>CsqPeekNextIrp</i> returns a pointer to the next matching IRP, or <b>NULL</b> if there is no matching IRP.</p>

<p>If the return value of <i>CsqPeekNextIrp</i> is non-<b>NULL</b>, <b>IoCsqRemoveNextIrp</b> calls the queue's <a href="..\wdm\nc-wdm-io-csq-remove-irp.md">CsqRemoveIrp</a> routine to remove the IRP.</p>

<p>Calls the queue's <a href="..\wdm\nc-wdm-io-csq-release-lock.md">CsqReleaseLock</a> routine to unlock the queue.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.</p>

<p>Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.</p>

<p>Callers of <b>IoCsqRemoveNextIrp</b> must be running at an IRQL &lt;= DISPATCH_LEVEL. The driver's callback routines must work correctly at that IRQL.</p>

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
<p>Available in Windows XP and later versions of Windows. Drivers that must also work on Windows 2000 and Windows 98/Me can instead link to Csq.lib to use the routine.</p>
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
<p>&lt;= DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocsqinitialize.md">IoCsqInitialize</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCsqRemoveNextIrp routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
