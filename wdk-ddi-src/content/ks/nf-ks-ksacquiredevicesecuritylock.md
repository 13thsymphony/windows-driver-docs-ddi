---
UID: NF:ks.KsAcquireDeviceSecurityLock
title: KsAcquireDeviceSecurityLock function
author: windows-driver-content
description: The KsAcquireDeviceSecurityLock function acquires the security lock associated with a device object.
old-location: stream\ksacquiredevicesecuritylock.htm
old-project: stream
ms.assetid: a5a003c1-fa35-461d-8a47-a1a7bc2375b4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAcquireDeviceSecurityLock, KsAcquireDeviceSecurityLock function [Streaming Media Devices], ks/KsAcquireDeviceSecurityLock, ksfunc_dd097c63-acd6-4de2-b3c9-a50e55e3f3f1.xml, stream.ksacquiredevicesecuritylock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAcquireDeviceSecurityLock
product: Windows
targetos: Windows
req.typenames: 
---


# KsAcquireDeviceSecurityLock function
The <b>KsAcquireDeviceSecurityLock</b> function acquires the security lock associated with a device object. An exclusive lock is acquired when changing a security descriptor. When manipulating the security of any object under a particular device object, this lock must be acquired.

## Syntax

```
KSDDKAPI VOID KsAcquireDeviceSecurityLock(
  KSDEVICE_HEADER Header,
  BOOLEAN         Exclusive
);
```

## Parameters

`Header`

Points to a driver-allocated device header, previously allocated by <b>KsAllocateDeviceHeader,</b> for the device object described by the KSDEVICE_HEADER structure.

`Exclusive`

Indicates, if set to <b>TRUE</b>, that the lock is to be acquired exclusively.


## Return Value

None

## Remarks

A shared lock is acquired when validating access during a create. An exclusive lock is acquired when changing a security descriptor.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560958">KsAllocateDeviceHeader</a>