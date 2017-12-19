---
UID: NF.wdm.IoInitializeRemoveLock
title: IoInitializeRemoveLock macro
author: windows-driver-content
description: The IoInitializeRemoveLock routine initializes a remove lock for a device object.
old-location: kernel\ioinitializeremovelock.htm
old-project: kernel
ms.assetid: d85bab78-0e9e-4e71-a09b-40954df81c87
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IoInitializeRemoveLock
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
req.product: Windows 10 or later.
---

# IoInitializeRemoveLock macro



## -description
The <b>IoInitializeRemoveLock</b> routine initializes a remove lock for a device object.



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

### -param Lock [in]

Pointer to a caller-supplied <b>IO_REMOVE_LOCK</b> structure that this routine initializes with information about the lock, including a counter and a synchronization event. A driver writer must allocate this structure as part of the device object's device extension.


### -param AllocateTag [in]

Specifies a tag to identify the creator of the lock. Driver writers typically use a 4-character string, specified in reverse order, like the tags used for <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>.

The I/O system uses this parameter if <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> is enabled, and on checked builds regardless of whether Driver Verifier is enabled. The caller should always supply a nonzero tag value for this parameter, for both free and checked builds.


### -param MaxLockedMinutes [in]

Specifies the maximum number of minutes that this lock should be held. A value of zero means there is no limit. This value is typically used during debugging to identify a driver routine that holds the lock longer than expected.

The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is held for more than <i>MaxLockedMinutes</i> on a checked build, the operating system asserts.


### -param HighWatermark [in]

Specifies the maximum number of outstanding acquisitions allowed on the lock. Use 0 to specify no maximum. <i>HighWatermark</i> must be &lt;= 0x7FFFFFFF.

The I/O system uses this parameter if Driver Verifier is enabled, and on checked builds regardless of whether Driver Verifier is enabled. If the lock is acquired <i>HighWatermark</i> times on a checked build, the operating system asserts.


## -remarks
A driver can use a remove lock to track outstanding I/O operations on a device and to determine when the driver can delete its device object in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.

Before calling <b>IoInitializeRemoveLock</b>, a driver should allocate an <b>IO_REMOVE_LOCK</b> structure in its <a href="https://msdn.microsoft.com/9ea59994-1112-4ae5-96a8-fa0670694b53">device extension</a>. A driver typically calls <b>IoInitializeRemoveLock</b> in its <a href="kernel.adddevice">AddDevice</a> routine, when the driver initializes the rest of the device extension for a device object.

After the <b>IoReleaseRemoveLockAndWait</b> routine returns, the driver should consider the device to be in a state in which it is ready to be removed and cannot perform I/O operations. Therefore, the driver must not call <b>IoInitializeRemoveLock</b> to re-initialize the remove lock. Violation of this rule while the driver is being verified by <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will result in a bug check.

Because the driver stores the <b>IO_REMOVE_LOCK</b> structure in the device extension of a device object, the remove lock is deleted when the driver deletes the device extension as part of processing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request.

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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ioacquireremovelock">IoAcquireRemoveLock</a>
</dt>
<dt>
<a href="kernel.ioinitializeremovelock">IoInitializeRemoveLock</a>
</dt>
<dt>
<a href="kernel.ioreleaseremovelock">IoReleaseRemoveLock</a>
</dt>
<dt>
<a href="kernel.ioreleaseremovelockandwait">IoReleaseRemoveLockAndWait</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInitializeRemoveLock routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

