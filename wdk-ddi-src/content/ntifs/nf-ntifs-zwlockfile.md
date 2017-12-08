---
UID: NF.ntifs.ZwLockFile
title: ZwLockFile function
author: windows-driver-content
description: The ZwLockFile routine requests a byte-range lock for the specified file.
old-location: kernel\zwlockfile.htm
old-project: kernel
ms.assetid: d5d4d13c-93d9-4531-85ff-d3fa0e52ecc1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ZwLockFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwLockFile,NtLockFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
---

# ZwLockFile function



## -description
The <b>ZwLockFile</b> routine requests a byte-range lock for the specified file.


## -syntax

````
NTSTATUS ZwLockFile(
  _In_     HANDLE           FileHandle,
  _In_opt_ HANDLE           Event,
  _In_opt_ PIO_APC_ROUTINE  ApcRoutine,
  _In_opt_ PVOID            ApcContext,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _In_     PLARGE_INTEGER   ByteOffset,
  _In_     PLARGE_INTEGER   Length,
  _In_     ULONG            Key,
  _In_     BOOLEAN          FailImmediately,
  _In_     BOOLEAN          ExclusiveLock
);
````


## -parameters

### -param FileHandle [in]

A handle for the file on which a byte-range lock is requested.

### -param Event [in, optional]

A handle to a caller-created event. If not <b>NULL</b>, the caller is placed into a wait state until the operation succeeds, at which time the event is set into the Signaled state.

### -param ApcRoutine [in, optional]

A pointer to a caller-supplied APC routine that is executed after the operation completes. Can be <b>NULL</b>.

### -param ApcContext [in, optional]

A pointer to a caller-specified context for the APC routine. This value is passed to the APC routine when it is executed. Can be <b>NULL</b>.

### -param IoStatusBlock [out]

A pointer to an <a href="kernel.io_status_block">IO_STATUS_BLOCK</a> structure that contains the final status.

### -param ByteOffset [in]

A pointer to a variable that specifies the starting byte offset of the range to lock.

### -param Length [in]

A pointer to a variable that specifies the length in bytes of the range to lock.

### -param Key [in]

A caller-assigned value used to describe groups of related locks. This value should be set to zero.

### -param FailImmediately [in]

If <b>TRUE</b>, immediately return if the file cannot be locked. If <b>FALSE</b>, wait for the lock request to be granted.

### -param ExclusiveLock [in]

If <b>TRUE</b>, byte-range lock is exclusive; otherwise, shared lock.

## -returns
The <b>ZwLockFile</b> routine returns STATUS_SUCCESS or an appropriate error NTSTATUS value. Possible NTSTATUS values include the following:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient resources exist to grant the byte-range lock for the specified file.
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>The byte-range lock was not granted for the specified file.

 

## -remarks
Callers of <b>ZwLockFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 7.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwunlockfile">ZwUnlockFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwLockFile routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
