---
UID: NF:ntddk.MmUnsecureVirtualMemory
title: MmUnsecureVirtualMemory function
author: windows-driver-content
description: The MmUnsecureVirtualMemory routine unsecures a memory address range secured by the MmSecureVirtualMemory routine.
old-location: kernel\mmunsecurevirtualmemory.htm
old-project: kernel
ms.assetid: 979eef24-e53b-476c-b9db-e56c43630913
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmUnsecureVirtualMemory, MmUnsecureVirtualMemory routine [Kernel-Mode Driver Architecture], k106_0bfc6e9e-a4e9-4868-b1fb-da6714146dbf.xml, kernel.mmunsecurevirtualmemory, ntddk/MmUnsecureVirtualMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. This routine is not available in Windows 98/Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnsecureVirtualMemory
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# MmUnsecureVirtualMemory function
The <b>MmUnsecureVirtualMemory</b> routine unsecures a memory address range secured by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a> routine.

## Syntax

```
NTKERNELAPI VOID MmUnsecureVirtualMemory(
  HANDLE SecureHandle
);
```

## Parameters

`SecureHandle`

Specifies the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a> for the memory address range.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. This routine is not available in Windows 98/Me.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |
| **DDI compliance rules** | IrqlMmApcLte, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a>