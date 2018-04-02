---
UID: NF:wdm.SeDeassignSecurity
title: SeDeassignSecurity function
author: windows-driver-content
description: The SeDeassignSecurity routine deallocates the memory associated with a security descriptor that was assigned using SeAssignSecurity.
old-location: kernel\sedeassignsecurity.htm
old-project: kernel
ms.assetid: c7060b86-8ff6-4229-94e0-7965ae59aa90
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: SeDeassignSecurity, SeDeassignSecurity routine [Kernel-Mode Driver Architecture], k110_9c1ca048-addd-4343-bfee-34e905b143b3.xml, kernel.sedeassignsecurity, wdm/SeDeassignSecurity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeDeassignSecurity
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# SeDeassignSecurity function
The  
   <b>SeDeassignSecurity</b> routine deallocates the memory associated with a security descriptor that was assigned using <b>SeAssignSecurity</b>.

## Syntax

```
NTKERNELAPI NTSTATUS SeDeassignSecurity(
  PSECURITY_DESCRIPTOR *SecurityDescriptor
);
```

## Parameters

`SecurityDescriptor`

Pointer to the buffered <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> being released.


## Return Value

If the deallocation succeeds, <b>SeDeassignSecurity</b> returns STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>