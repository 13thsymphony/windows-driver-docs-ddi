---
UID: NF:ntifs.SeAuditingFileEvents
title: SeAuditingFileEvents function
author: windows-driver-content
description: The SeAuditingFileEvents routine determines whether file open events are currently being audited.
old-location: ifsk\seauditingfileevents.htm
old-project: ifsk
ms.assetid: f9e9a53f-9f4a-4f44-befa-f11d1fb3372a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeAuditingFileEvents, SeAuditingFileEvents routine [Installable File System Drivers], ifsk.seauditingfileevents, ntifs/SeAuditingFileEvents, seref_b4b8468e-cfb2-4685-9811-2b2733e9fb36.xml
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeAuditingFileEvents
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeAuditingFileEvents function
The <b>SeAuditingFileEvents</b> routine determines whether file open events are currently being audited.

## Syntax

```
NTKERNELAPI BOOLEAN SeAuditingFileEvents(
  BOOLEAN              AccessGranted,
  PSECURITY_DESCRIPTOR SecurityDescriptor
);
```

## Parameters

`AccessGranted`

Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.

`SecurityDescriptor`

This parameter is ignored.


## Return Value

<b>SeAuditingFileEvents</b> returns <b>TRUE</b> if file open events are currently being audited, <b>FALSE</b> otherwise.

## Remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554778">SeAuditingFileOrGlobalEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556651">SeDeleteObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556682">SeOpenObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556685">SeOpenObjectForDeleteAuditAlarm</a>