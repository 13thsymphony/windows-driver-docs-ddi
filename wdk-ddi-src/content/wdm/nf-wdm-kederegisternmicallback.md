---
UID: NF:wdm.KeDeregisterNmiCallback
title: KeDeregisterNmiCallback function
author: windows-driver-content
description: The KeDeregisterNmiCallback routine deregisters a nonmaskable interrupt (NMI) callback registered by KeRegisterNmiCallback.
old-location: kernel\kederegisternmicallback.htm
old-project: kernel
ms.assetid: 45022490-8130-449c-8ec9-380be0a3a03d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeDeregisterNmiCallback, KeDeregisterNmiCallback routine [Kernel-Mode Driver Architecture], k105_407e4af5-fb93-4a7e-bacd-cc1d08935815.xml, kernel.kederegisternmicallback, wdm/KeDeregisterNmiCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte2, HwStorPortProhibitedDDIs
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
-	KeDeregisterNmiCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeDeregisterNmiCallback function
The <b>KeDeregisterNmiCallback</b> routine deregisters a nonmaskable interrupt (NMI) callback registered by <a href="..\wdm\nf-wdm-keregisternmicallback.md">KeRegisterNmiCallback</a>.

## Syntax

````
NTSTATUS KeDeregisterNmiCallback(
  _In_ PVOID Handle
);
````

## Parameters

`Handle`

Specifies the value returned by <a href="..\wdm\nf-wdm-keregisternmicallback.md">KeRegisterNmiCallback</a> when the NMI callback was registered.


## Return Value

The <b>KeDeregisterNmiCallback</b> routine returns STATUS_SUCCESS if the callback is successfully removed. It returns STATUS_INVALID_HANDLE if no callback matching the provided <i>Handle</i> value is found.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | IrqlKeApcLte2, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-keregisternmicallback.md">KeRegisterNmiCallback</a>