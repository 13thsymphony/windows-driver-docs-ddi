---
UID: NF:wdm.MmProtectMdlSystemAddress
title: MmProtectMdlSystemAddress function
author: windows-driver-content
description: The MmProtectMdlSystemAddress routine sets the protection type for a memory address range.
old-location: kernel\mmprotectmdlsystemaddress.htm
old-project: kernel
ms.assetid: e0ccc6e8-9351-4440-808b-e0b8eef48bc2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmProtectMdlSystemAddress, MmProtectMdlSystemAddress routine [Kernel-Mode Driver Architecture], k106_b2a56ec8-cfee-4547-b1c2-6f817ecbfaad.xml, kernel.mmprotectmdlsystemaddress, wdm/MmProtectMdlSystemAddress
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmProtectMdlSystemAddress
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmProtectMdlSystemAddress function
The <b>MmProtectMdlSystemAddress</b> routine sets the protection type for a memory address range.

## Syntax

```
NTKERNELAPI NTSTATUS MmProtectMdlSystemAddress(
  PMDL  MemoryDescriptorList,
  ULONG NewProtect
);
```

## Parameters

`MemoryDescriptorList`

Specifies the memory address range to set the protection type for.

`NewProtect`

Specifies the new protection setting for the memory pages. Drivers should specify one of the following values:





#### PAGE_NOACCESS

The underlying memory pages cannot be read or written. 



#### PAGE_READONLY

The underlying memory pages can only be read, not written. 



#### PAGE_READWRITE

The underlying memory pages can be read or written. 



#### PAGE_EXECUTE

The underlying memory pages can be executed, but not read or written.



#### PAGE_EXECUTE_READ

The underlying memory pages can be executed or read, but not written.



#### PAGE_EXECUTE_READWRITE

The underlying memory pages can be executed, read, or written.


## Return Value

<b>MmProtectMdlSystemAddress</b> returns an NTSTATUS code. The possible return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully changed the protection type for the memory address range.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PAGE_PROTECTION</b></dt>
</dl>
</td>
<td width="60%">
The value specified for <i>NewProtect</i> is not a valid one for this routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_MAPPED_VIEW</b></dt>
</dl>
</td>
<td width="60%">
The MDL has not yet been mapped. <b>MmProtectMdlSystemAddress</b> can only be used on MDLs that have already been mapped.

</td>
</tr>
</table>

## Remarks

The <b>MmProtectMdlSystemAddress</b> routine can only be called on an MDL that has already been mapped. For example, the routine can be called on an MDL mapped by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554629">MmMapLockedPagesSpecifyCache</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554629">MmMapLockedPagesSpecifyCache</a>