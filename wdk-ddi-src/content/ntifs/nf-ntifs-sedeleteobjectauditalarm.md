---
UID: NF:ntifs.SeDeleteObjectAuditAlarm
title: SeDeleteObjectAuditAlarm function
author: windows-driver-content
description: The SeDeleteObjectAuditAlarm routine generates audit and alarm messages for an object that is marked for deletion.
old-location: ifsk\sedeleteobjectauditalarm.htm
old-project: ifsk
ms.assetid: 3d0a26e2-60d4-437e-b5cc-3ca7afee8f5a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeDeleteObjectAuditAlarm, SeDeleteObjectAuditAlarm routine [Installable File System Drivers], ifsk.sedeleteobjectauditalarm, ntifs/SeDeleteObjectAuditAlarm, seref_eb1715b3-9c8b-4848-8cc8-3809d0d35d9e.xml
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
-	SeDeleteObjectAuditAlarm
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeDeleteObjectAuditAlarm function
The <b>SeDeleteObjectAuditAlarm</b> routine generates audit and alarm messages for an object that is marked for deletion.

## Syntax

````
VOID SeDeleteObjectAuditAlarm(
  _In_ PVOID  Object,
  _In_ HANDLE Handle
);
````

## Parameters

`Object`

Address of the object.

`Handle`

A unique 32-bit value representing the client's handle to the object.


## Return Value

None

## Remarks

Callers of <b>SeDeleteObjectAuditAlarm</b> must have <b>SeAuditPrivilege</b> enabled. The test for this privilege is always performed against the primary token of the calling process, allowing the calling process to impersonate a client. 

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

<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-seauditingfileevents.md">SeAuditingFileEvents</a>



<a href="..\ntifs\nf-ntifs-seauditingfileorglobalevents.md">SeAuditingFileOrGlobalEvents</a>



<a href="..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md">SeOpenObjectForDeleteAuditAlarm</a>