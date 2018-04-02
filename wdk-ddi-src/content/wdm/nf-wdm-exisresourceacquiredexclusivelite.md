---
UID: NF:wdm.ExIsResourceAcquiredExclusiveLite
title: ExIsResourceAcquiredExclusiveLite function
author: windows-driver-content
description: The ExIsResourceAcquiredExclusiveLite routine returns whether the current thread has exclusive access to a given resource.
old-location: kernel\exisresourceacquiredexclusivelite.htm
old-project: kernel
ms.assetid: 81c07809-1c66-4b68-b2d9-05992c778ae6
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExIsResourceAcquiredExclusiveLite, ExIsResourceAcquiredExclusiveLite routine [Kernel-Mode Driver Architecture], k102_ef023047-60ff-42aa-8224-37e2cfbe9f7b.xml, kernel.exisresourceacquiredexclusivelite, wdm/ExIsResourceAcquiredExclusiveLite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExIsResourceAcquiredExclusiveLite
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExIsResourceAcquiredExclusiveLite function
The <b>ExIsResourceAcquiredExclusiveLite</b> routine returns whether the current thread has exclusive access to a given resource.

## Syntax

```
NTKERNELAPI BOOLEAN ExIsResourceAcquiredExclusiveLite(
  PERESOURCE Resource
);
```

## Parameters

`Resource`

A pointer to the resource to be queried.


## Return Value

<b>ExIsResourceAcquiredExclusiveLite</b> returns <b>TRUE</b> if the caller already has exclusive access to the given resource.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545477">ExIsResourceAcquiredSharedLite</a>