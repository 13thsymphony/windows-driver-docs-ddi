---
UID: NF:wdm.KeQueryTotalCycleTimeThread
title: KeQueryTotalCycleTimeThread function
author: windows-driver-content
description: The KeQueryTotalCycleTimeThread routine returns the accumulated cycle time for the specified thread.
old-location: kernel\kequerytotalcycletimethread_.htm
old-project: kernel
ms.assetid: EC3A5F02-3D04-466E-8EB4-4BDA9CE47886
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KeQueryTotalCycleTimeThread, kernel.kequerytotalcycletimethread_, KeQueryTotalCycleTimeThread, KeQueryTotalCycleTimeThread routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KeQueryTotalCycleTimeThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeQueryTotalCycleTimeThread function
The <b>KeQueryTotalCycleTimeThread</b> routine returns the accumulated cycle time for the specified thread.

## Syntax

````
ULONG64 KeQueryTotalCycleTimeThread (
  _Inout_ PKTHREAD Thread,
  _Out_   PULONG64 CycleTimeStamp
);
````

## Parameters

`Thread`

A pointer to a dispatcher object of type KTHREAD.

`CycleTimeStamp`

A pointer to the cycle counter value at the time of the query.


## Return Value

The accumulated cycle time for the thread.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.exe |