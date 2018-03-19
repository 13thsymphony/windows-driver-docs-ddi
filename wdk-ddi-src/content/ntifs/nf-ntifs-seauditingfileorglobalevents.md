---
UID: NF:ntifs.SeAuditingFileOrGlobalEvents
title: SeAuditingFileOrGlobalEvents function
author: windows-driver-content
description: The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited.
old-location: ifsk\seauditingfileorglobalevents.htm
old-project: ifsk
ms.assetid: 4797126f-c27d-4951-88e7-37c5a475e77d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeAuditingFileOrGlobalEvents, SeAuditingFileOrGlobalEvents routine [Installable File System Drivers], ifsk.seauditingfileorglobalevents, ntifs/SeAuditingFileOrGlobalEvents, seref_06c1ee74-261c-4a57-b009-f76420e14055.xml
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
-	SeAuditingFileOrGlobalEvents
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeAuditingFileOrGlobalEvents function
The <b>SeAuditingFileOrGlobalEvents</b> routine determines whether file or global events are currently being audited.

## Syntax

````
BOOLEAN SeAuditingFileOrGlobalEvents(
  _In_ BOOLEAN                   AccessGranted,
  _In_ PSECURITY_DESCRIPTOR      SecurityDescriptor,
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext
);
````

## Parameters

`AccessGranted`

Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.

`SecurityDescriptor`

Pointer to the security descriptor protecting the object being accessed.

`SubjectSecurityContext`

Pointer to the subject's captured security context.


## Return Value

<b>SeAuditingFileOrGlobalEvents</b> returns <b>TRUE</b> if file or global events are currently being audited, <b>FALSE</b> otherwise.

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

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md">SeOpenObjectForDeleteAuditAlarm</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-seauditingfileevents.md">SeAuditingFileEvents</a>



<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>



<a href="..\ntifs\nf-ntifs-sedeleteobjectauditalarm.md">SeDeleteObjectAuditAlarm</a>