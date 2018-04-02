---
UID: NF:ntifs.PsRevertToSelf
title: PsRevertToSelf function
author: windows-driver-content
description: The PsRevertToSelf routine ends the calling thread's impersonation of a client.
old-location: ifsk\psreverttoself.htm
old-project: ifsk
ms.assetid: 21ae3a61-55c6-437d-8c1e-84d720de9dd5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsRevertToSelf, PsRevertToSelf routine [Installable File System Drivers], ifsk.psreverttoself, ntifs/PsRevertToSelf, psref_da555465-d8ee-4ae6-af44-cf0af7633458.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
-	PsRevertToSelf
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsRevertToSelf function
The <b>PsRevertToSelf</b> routine ends the calling thread's impersonation of a client.

## Syntax

```
NTKERNELAPI VOID PsRevertToSelf(

);
```

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

A server thread can impersonate a client by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a> routine. When the thread is done impersonating the client, it can call the <b>PsRevertToSelf</b> routine to end all impersonations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a>