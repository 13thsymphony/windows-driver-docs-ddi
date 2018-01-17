---
UID: NF:ntddk.KeEnterGuardedRegion
title: KeEnterGuardedRegion function
author: windows-driver-content
description: The KeEnterGuardedRegion routine enters a guarded region, which disables all kernel-mode APC delivery to the current thread.
old-location: kernel\keenterguardedregion.htm
old-project: kernel
ms.assetid: 9a21495e-8a4d-4177-a2c5-b6a928d86fd9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeEnterGuardedRegion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeEnterGuardedRegion
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: GuardedRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# KeEnterGuardedRegion function



## -description
The <b>KeEnterGuardedRegion</b> routine enters a guarded region, which disables all kernel-mode APC delivery to the current thread. 



## -syntax

````
VOID KeEnterGuardedRegion(void);
````


## -parameters


## -returns
None

None

None


## -remarks
To exit a guarded region entered with <b>KeEnterGuardedRegion</b>, call the <b>KeLeaveGuardedRegion</b> routine. Guarded regions can be nested. APCs are not reenabled until the thread exits the outermost guarded region.

For more information about guarded regions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542925">Critical Regions and Guarded Regions</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keleaveguardedregion.md">KeLeaveGuardedRegion</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeEnterGuardedRegion routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

