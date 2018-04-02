---
UID: NF:ntifs.SeOpenObjectAuditAlarm
title: SeOpenObjectAuditAlarm function
author: windows-driver-content
description: The SeOpenObjectAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object.
old-location: ifsk\seopenobjectauditalarm.htm
old-project: ifsk
ms.assetid: a4310cf8-1518-4d25-b2f9-a232ddd9c535
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeOpenObjectAuditAlarm, SeOpenObjectAuditAlarm routine [Installable File System Drivers], ifsk.seopenobjectauditalarm, ntifs/SeOpenObjectAuditAlarm, seref_87dbea09-cd36-40c2-8241-16c8180f1945.xml
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
-	SeOpenObjectAuditAlarm
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeOpenObjectAuditAlarm function
The <b>SeOpenObjectAuditAlarm</b> routine generates audit and alarm messages when an attempt is made to open an object.

## Syntax

```
NTKERNELAPI VOID SeOpenObjectAuditAlarm(
  PUNICODE_STRING      ObjectTypeName,
  PVOID                Object,
  PUNICODE_STRING      AbsoluteObjectName,
  PSECURITY_DESCRIPTOR SecurityDescriptor,
  PACCESS_STATE        AccessState,
  BOOLEAN              ObjectCreated,
  BOOLEAN              AccessGranted,
  KPROCESSOR_MODE      AccessMode,
  PBOOLEAN             GenerateOnClose
);
```

## Parameters

`ObjectTypeName`

Pointer to a null-terminated string specifying the type of object to which the client is requesting access. This string appears in any audit message that is generated.

`Object`

Address of the object being opened. This value is needed only to enter into log messages. If the open attempt fails, the value of <i>Object</i> is ignored. Otherwise, it must be provided.

`AbsoluteObjectName`

Pointer to a null-terminated string specifying the name of the object being opened. This string appears in any audit message that is generated.

`SecurityDescriptor`

A pointer to the security descriptor structure for the object being opened.

`AccessState`

Pointer to an access state structure containing the object's subject context, remaining desired access types, granted access types, and, optionally, a privilege set to indicate which privileges were used to permit the access.

`ObjectCreated`

Set to <b>TRUE</b> if the open operation causes a new object to be created, or <b>FALSE</b> if an existing object is opened.

`AccessGranted`

Set to <b>TRUE</b> if open access was granted based on a previous access check or privilege check, or <b>FALSE</b> if it was denied.

`AccessMode`

Access mode used for the access check. Either <b>UserMode</b> or <b>KernelMode</b>.

`GenerateOnClose`

Pointer to a flag set by the audit generation routine when <b>SeOpenObjectAuditAlarm</b> returns.


## Return Value

None

## Remarks

<b>SeOpenObjectAuditAlarm</b> generates any necessary audit or alarm messages for user-mode accesses. No messages are generated for kernel-mode accesses.

Before calling <b>SeOpenObjectAuditAlarm</b>, the caller must call <b>SeLockSubjectContext</b> to lock the caller's primary and impersonation tokens. After calling <b>SeOpenObjectAuditAlarm</b>, the caller must call <b>SeUnlockSubjectContext</b> to release these tokens.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538840">ACCESS_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554770">SeAuditingFileEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554778">SeAuditingFileOrGlobalEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556651">SeDeleteObjectAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556675">SeLockSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556685">SeOpenObjectForDeleteAuditAlarm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556707">SeSetAccessStateGenericMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556736">SeUnlockSubjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>