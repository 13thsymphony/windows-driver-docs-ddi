---
UID: NF:wdm.KeGetRecommendedSharedDataAlignment
title: KeGetRecommendedSharedDataAlignment function
author: windows-driver-content
description: The KeGetRecommendedSharedDataAlignment routine returns the preferred alignment for memory structures that can be accessed by more than one processor.
old-location: kernel\kegetrecommendedshareddataalignment.htm
old-project: kernel
ms.assetid: 2faf5e30-bfbb-4b23-9cb9-bf9dd81a56c2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeGetRecommendedSharedDataAlignment, kernel.kegetrecommendedshareddataalignment, k105_537a55c5-9c7e-49cb-8a27-de61e92b78e2.xml, KeGetRecommendedSharedDataAlignment routine [Kernel-Mode Driver Architecture], wdm/KeGetRecommendedSharedDataAlignment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeGetRecommendedSharedDataAlignment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeGetRecommendedSharedDataAlignment function
The <b>KeGetRecommendedSharedDataAlignment</b> routine returns the preferred alignment for memory structures that can be accessed by more than one processor.

## Syntax

````
ULONG KeGetRecommendedSharedDataAlignment(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeGetRecommendedSharedDataAlignment</b> returns the preferred alignment, in bytes, for memory structures that can be shared by more than one processor.

## Remarks

Use <b>KeGetRecommendedSharedDataAlignment</b> to determine the best alignment for data structures that will be shared between processors. The value returned minimizes cache effects that negatively impact performance on multiprocessor systems.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows. Available in Windows XP and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |