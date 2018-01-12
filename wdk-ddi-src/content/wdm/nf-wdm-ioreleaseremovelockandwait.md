---
UID: NF:wdm.IoReleaseRemoveLockAndWait
title: IoReleaseRemoveLockAndWait macro
author: windows-driver-content
description: The IoReleaseRemoveLockAndWait routine releases a remove lock that the driver acquired in a previous call to IoAcquireRemoveLock, and waits until all acquisitions of the lock have been released.
old-location: kernel\ioreleaseremovelockandwait.htm
old-project: kernel
ms.assetid: 79edb8b3-24a1-4dc0-b816-f78bbc888d3a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoReleaseRemoveLockAndWait
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoReleaseRemoveLockAndWait
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IoReleaseRemoveLockAndWaitOutsideRemoveDevice, RemoveLock, RemoveLockCheck, RemoveLockMnRemove, RemoveLockMnRemove2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReleaseRemoveLockAndWait macro



## -description
The <b>IoReleaseRemoveLockAndWait</b> routine releases a remove lock that the driver acquired in a previous call to <a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>, and waits until all acquisitions of the lock have been released.



## -syntax

````
VOID IoReleaseRemoveLockAndWait(
  _In_ PIO_REMOVE_LOCK RemoveLock,
  _In_ PVOID           Tag
);
````


## -parameters

### -param RemoveLock [in]

Pointer to an <b>IO_REMOVE_LOCK</b> structure that the caller passed in a previous call to <b>IoAcquireRemoveLock</b>. 


### -param Tag [in]

Pointer to a caller-supplied tag that was passed in a previous call to <b>IoAcquireRemoveLock</b>. 

If a driver specified a <i>Tag</i> when it acquired the lock, the driver must specify the same <i>Tag</i> when releasing the lock. If the tags do not match, this routine asserts on a checked build.

If the call to <b>IoAcquireRemoveLock</b> did not specify a <i>Tag</i>, then this parameter is <b>NULL</b>.

The I/O system only uses this parameter on checked builds.


## -remarks
A driver typically calls this routine in its dispatch code for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request. To allow queued I/O requests to complete, each driver should call <b>IoReleaseRemoveLockAndWait</b> <i>after</i> it passes the remove IRP to the next-lower driver, and <i>before</i> it releases memory, calls <a href="..\wdm\nf-wdm-iodetachdevice.md">IoDetachDevice</a>, or calls <a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>. The <b>IoReleaseRemoveLockAndWait</b> routine waits for the bus driver to cancel any IRPs that might be outstanding (for example, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a> IRP).

A driver must acquire the remove lock before calling <b>IoReleaseRemoveLockAndWait</b>. Typically, a driver calls <a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a> early in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff543341">DispatchPnp</a> routine, before the switch statement. As a result, the lock is acquired for each PnP operation, including the acquisition that is required before calling <b>IoReleaseRemoveLockAndWait</b> in the code that handles <b>IRP_MN_REMOVE_DEVICE</b>.

To release a lock from code other than the <b>IRP_MN_REMOVE_DEVICE</b> dispatch code, use <a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a>.

After <b>IoReleaseRemoveLockAndWait</b> has been called for a particular remove lock, subsequent calls to <b>IoAcquireRemoveLock</b> for the same remove lock will fail. <b>IoReleaseRemoveLockAndWait</b> does not return until all outstanding acquisitions of the remove lock have been released.

After <b>IoReleaseRemoveLockAndWait</b> returns, the driver should consider the device to be in a state in which it is ready to be removed and cannot perform I/O operations. Therefore, the driver must not call the <a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a> routine to re-initialize the remove lock. Violation of this rule while the driver is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will result in a bug check.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565504">Using Remove Locks</a>.


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
Version

</th>
<td width="70%">
Available starting with Windows 2000.

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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975175">IoReleaseRemoveLockAndWaitOutsideRemoveDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975206">RemoveLock</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975207">RemoveLockCheck</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975232">RemoveLockMnRemove</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975233">RemoveLockMnRemove2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975237">RemoveLockReleaseCleanup</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975238">RemoveLockReleaseClose</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975239">RemoveLockReleaseCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975240">RemoveLockReleaseDeviceControl</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975241">RemoveLockReleaseInternalDeviceControl</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975243">RemoveLockReleasePower</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975244">RemoveLockReleaseRead</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975245">RemoveLockReleaseShutdown</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975246">RemoveLockReleaseSystemControl</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975247">RemoveLockReleaseWrite</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543341">DispatchPnp</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iodetachdevice.md">IoDetachDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReleaseRemoveLockAndWait routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

