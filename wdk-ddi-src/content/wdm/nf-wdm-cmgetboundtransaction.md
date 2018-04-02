---
UID: NF:wdm.CmGetBoundTransaction
title: CmGetBoundTransaction function
author: windows-driver-content
description: The CmGetBoundTransaction routine returns a pointer to the transaction object that represents the transaction, if any, that is associated with a specified registry key object.
old-location: kernel\cmgetboundtransaction.htm
old-project: kernel
ms.assetid: f38a5ad6-6816-4b27-98ea-51ac1453d90f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: CmGetBoundTransaction, CmGetBoundTransaction routine [Kernel-Mode Driver Architecture], ConfigMgrRef_bf8b79d4-04cf-4cd2-b25c-4e59c63f0b86.xml, kernel.cmgetboundtransaction, wdm/CmGetBoundTransaction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
-	CmGetBoundTransaction
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# CmGetBoundTransaction function
The <b>CmGetBoundTransaction</b> routine returns a pointer to the transaction object that represents the <a href="https://msdn.microsoft.com/b558ace9-b416-4572-ac94-58a083c9d33b">transaction</a>, if any, that is associated with a specified registry key object.

## Syntax

```
NTKERNELAPI PVOID CmGetBoundTransaction(
  PLARGE_INTEGER Cookie,
  PVOID          Object
);
```

## Parameters

`Cookie`

The cookie value that the driver previously obtain by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a>.

`Object`

The pointer value that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> callback routine received in one of the <b>REG_<i>XXX</i>_KEY_INFORMATION</b> structures.


## Return Value

<b>CmGetBoundTransaction</b> returns a pointer to a transaction object, if the key object that the <i>Object</i> parameter specifies is associated with a transaction. Otherwise, the routine returns <b>NULL</b>.

## Remarks

The <b>CmGetBoundTransaction</b> routine is available on Windows Vista and later versions of Windows.

For more information about <b>CmGetBoundTransaction</b> and filtering registry operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

For more information about transactions, see <a href="https://msdn.microsoft.com/b558ace9-b416-4572-ac94-58a083c9d33b">Kernel Transaction Manager Design Guide</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541918">CmRegisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541921">CmRegisterCallbackEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>