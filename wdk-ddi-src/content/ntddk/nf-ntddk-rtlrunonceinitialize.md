---
UID: NF:ntddk.RtlRunOnceInitialize
title: RtlRunOnceInitialize function
author: windows-driver-content
description: The RtlRunOnceInitialize routine initializes a RTL_RUN_ONCE structure.
old-location: kernel\rtlrunonceinitialize.htm
old-project: kernel
ms.assetid: 4d1a65af-a475-4360-9db3-d5b9e302697d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlRunOnceInitialize, RtlRunOnceInitialize routine [Kernel-Mode Driver Architecture], k109_7d98d21e-b6f2-4ccd-b447-0c1d612eed5b.xml, kernel.rtlrunonceinitialize, ntddk/RtlRunOnceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlRunOnceInitialize
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlRunOnceInitialize function
The <b>RtlRunOnceInitialize</b> routine initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> structure.

## Syntax

````
VOID RtlRunOnceInitialize(
  _Out_ PRTL_RUN_ONCE RunOnce
);
````

## Parameters

`RunOnce`

Pointer to the <b>RTL_RUN_ONCE</b> one-time initialization structure.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563635">RunOnceInitialization</a>



<a href="..\ntddk\nf-ntddk-rtlrunoncebegininitialize.md">RtlRunOnceBeginInitialize</a>



<a href="..\ntddk\nf-ntddk-rtlrunonceexecuteonce.md">RtlRunOnceExecuteOnce</a>



<a href="..\ntddk\nf-ntddk-rtlrunoncecomplete.md">RtlRunOnceComplete</a>