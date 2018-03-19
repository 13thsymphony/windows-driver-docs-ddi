---
UID: NF:ntifs.IoUnregisterFileSystem
title: IoUnregisterFileSystem function
author: windows-driver-content
description: The IoUnregisterFileSystem routine removes a file system's control device object from the global file system queue.
old-location: ifsk\iounregisterfilesystem.htm
old-project: ifsk
ms.assetid: f6a0bff7-85b6-479a-b952-9a3a637e339e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoUnregisterFileSystem, IoUnregisterFileSystem routine [Installable File System Drivers], ifsk.iounregisterfilesystem, ioref_8799f64d-023b-4a67-8761-0899951596ad.xml, ntifs/IoUnregisterFileSystem
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
-	IoUnregisterFileSystem
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoUnregisterFileSystem function
The <b>IoUnregisterFileSystem</b> routine removes a file system's control device object from the global file system queue.

## Syntax

````
VOID IoUnregisterFileSystem(
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to the control device object for the file system.


## Return Value

None

## Remarks

<b>IoUnregisterFileSystem</b> unregisters the file system as an active file system by removing the file system's control device object from the global file system queue, and decrements the reference count on the file system's control device object. 

<b>IoUnregisterFileSystem</b> calls the notification routines of file system filter drivers that have registered for this notification by calling <a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>.

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



<a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>



<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>