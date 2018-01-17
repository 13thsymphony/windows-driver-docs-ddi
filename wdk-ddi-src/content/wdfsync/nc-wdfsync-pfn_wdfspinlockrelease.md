---
UID: NC:wdfsync.PFN_WDFSPINLOCKRELEASE
title: PFN_WDFSPINLOCKRELEASE function
author: windows-driver-content
description: The WdfSpinLockRelease method releases a specified spin lock.
old-location: wdf\wdfspinlockrelease.htm
old-project: wdf
ms.assetid: 874026f0-2fb9-421f-9864-d3646e136a80
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFSPINLOCKRELEASE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfSpinLockRelease
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ReqSendWhileSpinlock, WdfSpinlock, WdfSpinlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFSPINLOCKRELEASE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfSpinLockRelease</b> method releases a specified spin lock.



## -syntax

````
VOID WdfSpinLockRelease(
  _In_ WDFSPINLOCK SpinLock
);
````


## -parameters

### -param SpinLock [in]

A handle to a framework spin-lock object, obtained by a previous call to <a href="..\wdfsync\nf-wdfsync-wdfspinlockcreate.md">WdfSpinLockCreate</a>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfSpinLockRelease</b> method releases the spin lock that a driver obtained by previously calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550040">WdfSpinLockAcquire</a>. <b>WdfSpinLockRelease</b> also restores the driver's IRQL to the value that it had before the driver called <b>WdfSpinLockAcquire</b>.

For more information about spin locks, see <a href="wdf.synchronization_techniques_for_wdf_drivers">Synchronization Techniques for Framework-Based Drivers</a>.

For a code example that uses <b>WdfSpinLockRelease</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550040">WdfSpinLockAcquire</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550040">WdfSpinLockAcquire</a>
</dt>
<dt>
<a href="..\wdfsync\nf-wdfsync-wdfspinlockcreate.md">WdfSpinLockCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfSpinLockRelease method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

