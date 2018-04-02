---
UID: NF:ntifs.IoGetDiskDeviceObject
title: IoGetDiskDeviceObject function
author: windows-driver-content
description: The IoGetDiskDeviceObject routine retrieves a pointer to the disk device object associated with a given file system volume device object.
old-location: ifsk\iogetdiskdeviceobject.htm
old-project: ifsk
ms.assetid: c4f27011-f198-474e-8d2c-8bf35c3c8c66
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoGetDiskDeviceObject, IoGetDiskDeviceObject routine [Installable File System Drivers], ifsk.iogetdiskdeviceobject, ioref_b3532bdd-87b6-4e6b-91a0-093b8ed5aa6c.xml, ntifs/IoGetDiskDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDiskDeviceObject
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoGetDiskDeviceObject function
The <b>IoGetDiskDeviceObject</b> routine retrieves a pointer to the disk device object associated with a given file system volume device object.

## Syntax

```
NTKERNELAPI NTSTATUS IoGetDiskDeviceObject(
  PDEVICE_OBJECT FileSystemDeviceObject,
  PDEVICE_OBJECT *DiskDeviceObject
);
```

## Parameters

`FileSystemDeviceObject`

A pointer to the file system device object.

`DiskDeviceObject`

TBD


## Return Value

<b>IoGetDiskDeviceObject</b> returns one of the following status values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this function was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
</table>

## Remarks

<b>IoGetDiskDeviceObject</b> returns a pointer to the storage device object associated with the file system volume. The storage device need not be an actual disk 

File system filter drivers typically call <b>IoGetDiskDeviceObject</b> for a file system volume device object to determine whether the volume is mounted. 

<b>IoGetDiskDeviceObject</b> increments the reference count on the disk device object pointed to by <i>DeviceObject</i>. Thus every successful call to <b>IoGetDiskDeviceObject</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548342">IoEnumerateDeviceObjectList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548359">IoGetAttachedDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549145">IoGetAttachedDeviceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548379">IoGetLowerDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>