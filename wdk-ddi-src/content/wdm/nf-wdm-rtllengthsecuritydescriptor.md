---
UID: NF:wdm.RtlLengthSecurityDescriptor
title: RtlLengthSecurityDescriptor function
author: windows-driver-content
description: The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor.
old-location: kernel\rtllengthsecuritydescriptor.htm
old-project: kernel
ms.assetid: e06888eb-2ced-46c0-bdbf-3bad57020bf7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlLengthSecurityDescriptor, RtlLengthSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_ea245194-f36b-4b47-9d81-2d72fc19d5bc.xml, kernel.rtllengthsecuritydescriptor, wdm/RtlLengthSecurityDescriptor
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
req.ddi-compliance: 
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
-	RtlLengthSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlLengthSecurityDescriptor function
The <b>RtlLengthSecurityDescriptor</b> routine returns the size of a given security descriptor.

## Syntax

```
NTSYSAPI ULONG RtlLengthSecurityDescriptor(
  PSECURITY_DESCRIPTOR SecurityDescriptor
);
```

## Parameters

`SecurityDescriptor`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>.


## Return Value

<b>RtlLengthSecurityDescriptor</b> returns the size in bytes of the descriptor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>