---
UID: NF:ntifs.IoUnregisterFsRegistrationChange
title: IoUnregisterFsRegistrationChange function
author: windows-driver-content
description: The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine.
old-location: ifsk\iounregisterfsregistrationchange.htm
old-project: ifsk
ms.assetid: 4e10afc0-b9c4-4495-83a1-11f9b82143fc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoUnregisterFsRegistrationChange, IoUnregisterFsRegistrationChange routine [Installable File System Drivers], ifsk.iounregisterfsregistrationchange, ioref_18a53f5a-49f9-40ba-bf85-d2fea7d6fbfb.xml, ntifs/IoUnregisterFsRegistrationChange
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
-	IoUnregisterFsRegistrationChange
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoUnregisterFsRegistrationChange function
The <b>IoUnregisterFsRegistrationChange</b> routine unregisters file system filter driver's file system registration change notification routine.

## Syntax

````
VOID IoUnregisterFsRegistrationChange(
  _In_ PDRIVER_OBJECT          DriverObject,
  _In_ PDRIVER_FS_NOTIFICATION DriverNotificationRoutine
);
````

## Parameters

`DriverObject`

Pointer to the driver object for the filter driver.

`DriverNotificationRoutine`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## Return Value

None

## Remarks

<b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a> or <a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>



<a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>



<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>