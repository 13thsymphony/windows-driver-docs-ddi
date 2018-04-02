---
UID: NF:ntifs.PsDereferenceImpersonationToken
title: PsDereferenceImpersonationToken function
author: windows-driver-content
description: The PsDereferenceImpersonationToken routine decrements the reference count of an impersonation token.
old-location: ifsk\psdereferenceimpersonationtoken.htm
old-project: ifsk
ms.assetid: 8320d4d1-f282-4977-96e7-de6f63d86ec4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsDereferenceImpersonationToken, PsDereferenceImpersonationToken routine [Installable File System Drivers], ifsk.psdereferenceimpersonationtoken, ntifs/PsDereferenceImpersonationToken, psref_8d62cb23-83a3-45fd-8b35-f7e38dd1548d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsDereferenceImpersonationToken
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsDereferenceImpersonationToken function
The <b>PsDereferenceImpersonationToken</b> routine decrements the reference count of an impersonation token.

## Syntax

```
NTKERNELAPI VOID PsDereferenceImpersonationToken(
  PACCESS_TOKEN ImpersonationToken
);
```

## Parameters

`ImpersonationToken`

Pointer to the impersonation token whose reference count is to be decremented. If this is a <b>NULL</b> pointer, <b>PsDereferenceImpersonationToken</b> does nothing.


## Return Value

None

## Remarks

If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551929">PsReferenceImpersonationToken</a>