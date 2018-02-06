---
UID: NF:wdm.SeDeassignSecurity
title: SeDeassignSecurity function
author: windows-driver-content
description: The SeDeassignSecurity routine deallocates the memory associated with a security descriptor that was assigned using SeAssignSecurity.
old-location: kernel\sedeassignsecurity.htm
old-project: kernel
ms.assetid: c7060b86-8ff6-4229-94e0-7965ae59aa90
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: SeDeassignSecurity, wdm/SeDeassignSecurity, kernel.sedeassignsecurity, SeDeassignSecurity routine [Kernel-Mode Driver Architecture], k110_9c1ca048-addd-4343-bfee-34e905b143b3.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	SeDeassignSecurity
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# SeDeassignSecurity function
The  
   <b>SeDeassignSecurity</b> routine deallocates the memory associated with a security descriptor that was assigned using <b>SeAssignSecurity</b>.

## Syntax

````
NTSTATUS SeDeassignSecurity(
  _Inout_ PSECURITY_DESCRIPTOR *SecurityDescriptor
);
````

## Parameters

`SecurityDescriptor`

Pointer to the buffered <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> being released.


## Return Value

If the deallocation succeeds, <b>SeDeassignSecurity</b> returns STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. Available in Windows 2000 and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeDeassignSecurity routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>