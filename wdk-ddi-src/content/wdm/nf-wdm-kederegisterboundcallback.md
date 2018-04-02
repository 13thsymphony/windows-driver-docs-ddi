---
UID: NF:wdm.KeDeregisterBoundCallback
title: KeDeregisterBoundCallback function
author: windows-driver-content
description: The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback.
old-location: kernel\kederegisterboundcallback.htm
old-project: kernel
ms.assetid: 697709D4-DBB7-4CB4-83A1-89E8BAFD68DA
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeDeregisterBoundCallback, KeDeregisterBoundCallback routine [Kernel-Mode Driver Architecture], kernel.kederegisterboundcallback, wdm/KeDeregisterBoundCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeDeregisterBoundCallback
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeDeregisterBoundCallback function
The <b>KeDeregisterBoundCallback</b> routine deregisters a user-mode bound exception callback registered by <a href="https://msdn.microsoft.com/library/windows/hardware/dn957856">KeRegisterBoundCallback</a>.

## Syntax

```
NTKERNELAPI NTSTATUS KeDeregisterBoundCallback(
  PVOID Handle
);
```

## Parameters

`Handle`

Specifies the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/dn957856">KeRegisterBoundCallback</a> when the callback was registered.


## Return Value

The <b>KeDeregisterBoundCallback</b> routine returns STATUS_SUCCESS if the callback is successfully removed. It returns STATUS_INVALID_HANDLE if no callback matching the provided <i>Handle</i> value is found.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957856">KeRegisterBoundCallback</a>