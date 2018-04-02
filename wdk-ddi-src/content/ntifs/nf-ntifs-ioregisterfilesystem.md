---
UID: NF:ntifs.IoRegisterFileSystem
title: IoRegisterFileSystem function
author: windows-driver-content
description: The IoRegisterFileSystem routine adds a file system's control device object to the global file system queue.
old-location: ifsk\ioregisterfilesystem.htm
old-project: ifsk
ms.assetid: 19d53afd-b63c-4fd3-9b08-c51e2a1247af
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoRegisterFileSystem, IoRegisterFileSystem routine [Installable File System Drivers], ifsk.ioregisterfilesystem, ioref_42200300-9ef6-4be9-8fee-bf42b027a809.xml, ntifs/IoRegisterFileSystem
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
-	IoRegisterFileSystem
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoRegisterFileSystem function
The <b>IoRegisterFileSystem</b> routine adds a file system's control device object to the global file system queue.

## Syntax

```
NTKERNELAPI VOID IoRegisterFileSystem(
  __drv_aliasesMem PDEVICE_OBJECT DeviceObject
);
```

## Parameters

`DeviceObject`

Pointer to the control device object for the file system.


## Return Value

None

## Remarks

<b>IoRegisterFileSystem</b> registers a file system as an active file system by inserting the file system's control device object into the global file system queue, and increments the reference count on the file system's control device object.

The file system control device object's device type must be one of the following:

FILE_DEVICE_NETWORK_FILE_SYSTEM

FILE_DEVICE_CD_ROM_FILE_SYSTEM

FILE_DEVICE_DISK_FILE_SYSTEM

If the device type is not one of these values, the file system is not registered.

In addition, the file system control device object must be named. If it is not named, this does not cause the call to <b>IoRegisterFileSystem</b> to fail. However, file system filter drivers, as well as many system components and support routines, use this name to distinguish the file system's control device objects, which are always named, from its volume device objects, which are never named. 

If the DO_LOW_PRIORITY_FILESYSTEM flag is set on the file system's control device object, the device object is inserted into the next-to-last position in the queue. (The RAW file system occupies the last position in the queue.) If this flag is not set, the device object is inserted at the head of the queue.

<b>IoRegisterFileSystem</b> calls the notification routines of file system filter drivers that have registered for this notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548508">IoRegisterFsRegistrationChangeEx</a>.

<div class="alert"><b>Note</b>    In Microsoft Windows XP and later, when a file system filter driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>, its notification routine is also called immediately for any file systems that have already called <b>IoRegisterFileSystem</b>. </div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548499">IoRegisterFsRegistrationChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548508">IoRegisterFsRegistrationChangeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548552">IoUnregisterFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548557">IoUnregisterFsRegistrationChange</a>