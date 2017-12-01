---
UID: NF.wdm.IoInitializeRemoveLock
title: IoInitializeRemoveLock
author: windows-driver-content
description: The IoInitializeRemoveLock routine initializes a remove lock for a device object.
old-location: kernel\ioinitializeremovelock.htm
old-project: kernel
ms.assetid: d85bab78-0e9e-4e71-a09b-40954df81c87
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IoInitializeRemoveLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoInitializeRemoveLock
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# IoInitializeRemoveLock function



## -description
<p>The <b>IoInitializeRemoveLock</b> routine initializes a remove lock for a device object.</p>


## -syntax

````
VOID IoInitializeRemoveLock(
  _In_ PIO_REMOVE_LOCK Lock,
  _In_ ULONG           AllocateTag,
  _In_ ULONG           MaxLockedMinutes,
  _In_ ULONG           HighWatermark
);
````


## -parameters
<dl>

### -param <i>Lock</i> [in]

<dd>
<p>Pointer to a caller-supplied <b>IO_REMOVE_LOCK</b> structure that this routine initializes with information about the lock, including a counter and a synchronization event. A driver writer must allocate this structure as part of the device object's device extension.</p>
</dd>

### -param <i>AllocateTag</i> [in]

<dd>
<p>Specifies a tag to identify the creator of the lock. Driver writers typically use a 4-character string, specified in reverse order, like the tags used for <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.</p>
<p>The I/O system uses this parameter if <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> is enabled, and on checked builds regardless of whether Driver Verifier is enabled. The caller should always supply a nonzero tag value for this parameter, for both free and checked builds.</p>
</dd>

### -param <i>MaxLockedMinutes</i> [in]

<dd>
<p>Specifies the maximum number of minutes that this lock should be held. A value of zero means there is no limit. This value is typically used during debugging to identify a driver routine that holds the lock longer than expected.</p>
<p>The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is held for more than <i>MaxLockedMinutes</i> on a checked build, the operating system asserts.</p>
</dd>

### -param <i>HighWatermark</i> [in]

<dd>
<p>Specifies the maximum number of outstanding acquisitions allowed on the lock. Use 0 to specify no maximum. <i>HighWatermark</i> must be &lt;= 0x7FFFFFFF.</p>
<p>The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is acquired <i>HighWatermark</i> times on a checked build, the operating system asserts.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A driver can use a remove lock to track outstanding I/O operations on a device and to determine when the driver can delete its device object in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.</p>

<p>Before calling <b>IoInitializeRemoveLock</b>, a driver should allocate an <b>IO_REMOVE_LOCK</b> structure in its <a href="https://msdn.microsoft.com/9ea59994-1112-4ae5-96a8-fa0670694b53">device extension</a>. A driver typically calls <b>IoInitializeRemoveLock</b> in its <a href="kernel.adddevice">AddDevice</a> routine, when the driver initializes the rest of the device extension for a device object.</p>

<p>After the <b>IoReleaseRemoveLockAndWait</b> routine returns, the driver should consider the device to be in a state in which it is ready to be removed and cannot perform I/O operations. Therefore, the driver must not call <b>IoInitializeRemoveLock</b> to re-initialize the remove lock. Violation of this rule while the driver is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will result in a bug check.</p>

<p>Because the driver stores the <b>IO_REMOVE_LOCK</b> structure in the device extension of a device object, the remove lock is deleted when the driver deletes the device extension as part of processing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565504">Using Remove Locks</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioacquireremovelock.md">IoAcquireRemoveLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioinitializeremovelock.md">IoInitializeRemoveLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioreleaseremovelock.md">IoReleaseRemoveLock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioreleaseremovelockandwait.md">IoReleaseRemoveLockAndWait</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInitializeRemoveLock routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
