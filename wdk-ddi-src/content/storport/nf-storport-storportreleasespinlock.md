---
UID: NF:storport.StorPortReleaseSpinLock
title: StorPortReleaseSpinLock function
author: windows-driver-content
description: The StorPortReleaseSpinLock routine releases a spinlock acquired by StorPortAcquireSpinLock.
old-location: storage\storportreleasespinlock.htm
old-project: storage
ms.assetid: ed91d41a-575d-4b26-a7e0-f3ce43db76b4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReleaseSpinLock, StorPortReleaseSpinLock routine [Storage Devices], storage.storportreleasespinlock, storport/StorPortReleaseSpinLock, storprt_5f3bd7a7-ffdd-4d7b-992b-70c2cea3acec.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortSpinLock, StorPortSpinLock4
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortReleaseSpinLock
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReleaseSpinLock function
The <b>StorPortReleaseSpinLock</b> routine releases a spinlock acquired by <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>.

## Syntax

````
VOID StorPortReleaseSpinLock(
  _In_    PVOID             HwDeviceExtension,
  _Inout_ PSTOR_LOCK_HANDLE LockHandle
);
````

## Parameters

`DeviceExtension`

TBD

`LockHandle`

Pointer to a lock handle returned by <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>.


## Return Value

None.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **DDI compliance rules** | StorPortSpinLock, StorPortSpinLock4 |

## See Also

<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>