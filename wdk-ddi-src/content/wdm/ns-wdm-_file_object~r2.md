---
UID: NS.WDM._FILE_OBJECT~R2
title: _FILE_OBJECT
author: windows-driver-content
description: The FILE_OBJECT structure is used by the system to represent a file object.
old-location: kernel\file_object.htm
old-project: kernel
ms.assetid: fa87a3e8-97d2-48c0-9722-2be011d145dd
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _FILE_OBJECT, *PFILE_OBJECT, FILE_OBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_OBJECT
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _FILE_OBJECT structure



## -description
The <b>FILE_OBJECT</b> structure is used by the system to represent a file object. To user-mode protected subsystems, a file object represents an open instance of a file, device, directory, or volume. To device and intermediate drivers, a file object usually represents a device object. To drivers in the file system stack, a file object usually represents a directory or file.
A file object is partially opaque. Certain types of drivers, such as file system drivers and network transport drivers, use some of the fields of file objects.


## -syntax

````
typedef struct _FILE_OBJECT {
  CSHORT                            Type;
  CSHORT                            Size;
  PDEVICE_OBJECT                    DeviceObject;
  PVPB                              Vpb;
  PVOID                             FsContext;
  PVOID                             FsContext2;
  PSECTION_OBJECT_POINTERS          SectionObjectPointer;
  PVOID                             PrivateCacheMap;
  NTSTATUS                          FinalStatus;
  struct _FILE_OBJECT  *RelatedFileObject;
  BOOLEAN                           LockOperation;
  BOOLEAN                           DeletePending;
  BOOLEAN                           ReadAccess;
  BOOLEAN                           WriteAccess;
  BOOLEAN                           DeleteAccess;
  BOOLEAN                           SharedRead;
  BOOLEAN                           SharedWrite;
  BOOLEAN                           SharedDelete;
  ULONG                             Flags;
  UNICODE_STRING                    FileName;
  LARGE_INTEGER                     CurrentByteOffset;
  __volatile ULONG                  Waiters;
  __volatile ULONG                  Busy;
  PVOID                             LastLock;
  KEVENT                            Lock;
  KEVENT                            Event;
  __volatile PIO_COMPLETION_CONTEXT CompletionContext;
  KSPIN_LOCK                        IrpListLock;
  LIST_ENTRY                        IrpList;
  __volatile PVOID                  FileObjectExtension;
} FILE_OBJECT, *PFILE_OBJECT;
````


## -struct-fields

### -field Type

A read-only member used by the system to indicate that the object is a file object. If the object is a file object, the value of this member is 5.

### -field Size

A read-only member that specifies the size, in bytes, of the file object. This size does not include the file object extension, if one is present.

### -field DeviceObject

A pointer to the device object on which the file is opened.

### -field Vpb

A pointer to the volume parameter block associated with the file object.
Note that if the <b>Vpb</b> member is non-<b>NULL</b>, the file resides on a mounted volume.

### -field FsContext

A pointer to whatever optional state a driver maintains about the file object; otherwise, 
      <b>NULL</b>. For file system drivers, this member <u>must</u> point to a 
      <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> header structure that is contained within a file-system-specific structure; otherwise system instability can result. Usually, this header structure is embedded in a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, this header structure is a stream control block (SCB).
      
<div class="alert"><b>Note</b>  In a WDM device stack, only the functional device object (FDO) can use the two context pointers. File system drivers share this member across multiple opens to the same data stream.</div>
<div> </div>

### -field FsContext2

A pointer to whatever additional state a driver maintains about the file object; otherwise, 
      <b>NULL</b>.
      
<div class="alert"><b>Note</b>  This member is opaque for drivers in the file system stack because the underlying file system utilizes this member.</div>
<div> </div>

### -field SectionObjectPointer

A pointer to the file object's read-only section object. This member is set only by file systems and used for Cache Manager interaction.

### -field PrivateCacheMap

An opaque member, set only by file systems, that points to handle-specific information and that is used for Cache Manager interaction.

### -field FinalStatus

A read-only member that is used, in certain synchronous cases, to indicate the final status of the file object's I/O request.

### -field RelatedFileObject

A pointer to a <b>FILE_OBJECT</b> structure used to indicate that the current file object has been opened relative to an already open file object. The file object pointed to by this member is usually a directory (meaning the current file has been opened relative to this directory). However, a file can be reopened relative to itself, and alternate data streams for a file can be opened relative to an already open primary data stream for that same file. The <b>RelatedFileObject</b> member is only valid during the processing of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> requests.

### -field LockOperation

A read-only member. If <b>FALSE</b>, a lock operation 
      (<b>NtLockFile</b>) has never been performed on the file object. If 
      <b>TRUE</b>, at least one lock operation has been performed on the file object. Once set to 
      <b>TRUE</b>, this member always remains <b>TRUE</b> (for example, releasing file locks on the file object does not reset this member to <b>FALSE</b>).

### -field DeletePending

A read-only member. If <b>TRUE</b>, a delete operation for the file associated with the file object exists. If <b>FALSE</b>, there currently is no pending delete operation for the file object.

### -field ReadAccess

A read-only member. If <b>TRUE</b>, the file associated with the file object has been opened for read access. If <b>FALSE</b>, the file has been opened without read access. This information is used when checking and/or setting the share access of the file.

### -field WriteAccess

A read-only member. If <b>TRUE</b>, the file associated with the file object has been opened for write access. If <b>FALSE</b>, the file has been opened without write access. This information is used when checking and/or setting the share access of the file.

### -field DeleteAccess

A read-only member. If <b>TRUE</b>, the file associated with the file object has been 
      opened for delete access. If <b>FALSE</b>, the file has been opened without delete access. 
      This information is used when checking and/or setting the share access of the file.

### -field SharedRead

A read-only member. If <b>TRUE</b>, the file associated with the file object has been opened for read sharing access. If <b>FALSE</b>, the file has been opened without read sharing access. This information is used when checking and/or setting the share access of the file.

### -field SharedWrite

A read-only member. If <b>TRUE</b>, the file associated with the file object has been opened for write sharing access. If <b>FALSE</b>, the file has been opened without write sharing access. This information is used when checking and/or setting the share access of the file. 

### -field SharedDelete

A read-only member. If <b>TRUE</b>, the file associated with the file object has been opened for delete sharing access. If <b>FALSE</b>, the file has been opened without delete sharing access. This information is used when checking and/or setting the share access of the file.

### -field Flags

A read-only member used by the system to hold one or more (a bitwise inclusive OR combination) of the following private flag values.
      
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FO_FILE_OPEN</b>
</td>
<td>
Deprecated.
</td>
</tr>
<tr>
<td>
<b>FO_SYNCHRONOUS_IO</b>
</td>
<td>
The file object is opened for synchronous I/O.
</td>
</tr>
<tr>
<td>
<b>FO_ALERTABLE_IO</b>
</td>
<td>
Any wait in the I/O manager, as a result of a request made to this file object, is alertable.
</td>
</tr>
<tr>
<td>
<b>FO_NO_INTERMEDIATE_BUFFERING</b>
</td>
<td>
The file associated with the file object cannot be cached or buffered in a driver's internal buffers.
</td>
</tr>
<tr>
<td>
<b>FO_WRITE_THROUGH</b>
</td>
<td>
System services, file system drivers, and drivers that write data to the file must transfer the data into 
          the file before any requested write operation is considered complete.
</td>
</tr>
<tr>
<td>
<b>FO_SEQUENTIAL_ONLY</b>
</td>
<td>
The file associated with the file object was opened for sequential I/O operations only.
</td>
</tr>
<tr>
<td>
<b>FO_CACHE_SUPPORTED</b>
</td>
<td>
The file associated with the file object is cacheable. This flag should be set only by a file system 
          driver, and only if the <b>FsContext</b> member points to a valid 
          <a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure.
</td>
</tr>
<tr>
<td>
<b>FO_NAMED_PIPE</b>
</td>
<td>
The file object represents a named pipe.
</td>
</tr>
<tr>
<td>
<b>FO_STREAM_FILE</b>
</td>
<td>
The file object represents a file stream.
</td>
</tr>
<tr>
<td>
<b>FO_MAILSLOT</b>
</td>
<td>
The file object represents a mailslot.
</td>
</tr>
<tr>
<td>
<b>FO_GENERATE_AUDIT_ON_CLOSE</b>
</td>
<td>
Deprecated.
</td>
</tr>
<tr>
<td>
<b>FO_QUEUE_IRP_TO_THREAD</b>
</td>
<td>
IRPs will not be queued to this file object.
</td>
</tr>
<tr>
<td>
<b>FO_DIRECT_DEVICE_OPEN</b>
</td>
<td>
The device targeted by this file object was opened directly.
</td>
</tr>
<tr>
<td>
<b>FO_FILE_MODIFIED</b>
</td>
<td>
The file associated with the file object has been modified.
</td>
</tr>
<tr>
<td>
<b>FO_FILE_SIZE_CHANGED</b>
</td>
<td>
The file associated with the file object has changed in size.
</td>
</tr>
<tr>
<td>
<b>FO_CLEANUP_COMPLETE</b>
</td>
<td>
The file system has completed its cleanup for this file object.
</td>
</tr>
<tr>
<td>
<b>FO_TEMPORARY_FILE</b>
</td>
<td>
The file associated with the file object is a temporary file.
</td>
</tr>
<tr>
<td>
<b>FO_DELETE_ON_CLOSE</b>
</td>
<td>
The file associated with the file object will be deleted by the file system upon close.
</td>
</tr>
<tr>
<td>
<b>FO_OPENED_CASE_SENSITIVE</b>
</td>
<td>
The file name case of the file associated with the file object is respected.
</td>
</tr>
<tr>
<td>
<b>FO_HANDLE_CREATED</b>
</td>
<td>
A file handle was created for file object.
</td>
</tr>
<tr>
<td>
<b>FO_FILE_FAST_IO_READ</b>
</td>
<td>
A fast I/O read was performed on this file object.
</td>
</tr>
<tr>
<td>
<b>FO_RANDOM_ACCESS</b>
</td>
<td>
The file associated with the file object was opened for random access.
</td>
</tr>
<tr>
<td>
<b>FO_FILE_OPEN_CANCELLED</b>
</td>
<td>
The create request for this file object was canceled before completing.
</td>
</tr>
<tr>
<td>
<b>FO_VOLUME_OPEN</b>
</td>
<td>
The file object represents a volume open request.
</td>
</tr>
<tr>
<td>
<b>FO_REMOTE_ORIGIN</b>
</td>
<td>
The create request for the file associated with the file object originated on a remote machine.
</td>
</tr>
<tr>
<td>
<b>FO_SKIP_COMPLETION_PORT</b>
</td>
<td>
For a file object associated with a port, determines if the system should skip queuing to the completion 
          port when the IRP is completed synchronously with a non-error status return value.
</td>
</tr>
<tr>
<td>
<b>FO_SKIP_SET_EVENT</b>
</td>
<td>
Skip setting the event for the file object upon IRP completion.
</td>
</tr>
<tr>
<td>
<b>FO_SKIP_SET_FAST_IO</b>
</td>
<td>
Skip setting an event supplied to a system service when the fast I/O path is successful.
</td>
</tr>
</table>
 

### -field FileName

A <a href="kernel.unicode_string">UNICODE_STRING</a> structure whose <b>Buffer</b> member points to a read-only Unicode string that holds the name of the file opened on the volume. If the volume is being opened, the <b>Length</b> member of the 
      <b>UNICODE_STRING</b> structure will be zero. Note that the file name in this string is valid only during the initial processing of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request. This file name should <u>not</u> be considered valid after the file system starts to process the <b>IRP_MJ_CREATE</b> request. The storage for the string pointed to by the <b>Buffer</b> member of the <b>UNICODE_STRING</b> structure is allocated in paged system memory. For more information about obtaining a file name, see <a href="ifsk.fltgetfilenameinformation">FltGetFileNameInformation</a>.

### -field CurrentByteOffset

A read-only member that specifies the file offset, in bytes, associated with the file object.

### -field Waiters

A read-only member used by the system to count the number of outstanding waiters on a file object opened for synchronous access.

### -field Busy

A read-only member used by the system to indicate whether a file object opened for synchronous access is currently busy.

### -field LastLock

An opaque pointer to the last lock applied to the file object.

### -field Lock

An opaque member used by the system to hold a file object event lock. The event lock is used to control synchronous access to the file object. Applicable only to file objects that are opened for synchronous access.

### -field Event

An opaque member used by the system to hold an event object for the file object. The event object is used to signal the completion of an I/O request on the file object if no user event was supplied or a synchronous API was called.

### -field CompletionContext

An opaque pointer to completion port information (port pointer and key) associated with the file object, if any.

### -field IrpListLock

An opaque pointer to a <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">KSPIN_LOCK</a> structure that serves as the spin lock used to synchronize access to the file object's IRP list.

### -field IrpList

An opaque pointer to the head of the IRP list associated with the file object.

### -field FileObjectExtension

An opaque pointer to the file object's file object extension (<a href="ifsk.the_fobx_structure">FOBX</a>) structure. The <b>FOBX</b> structure contains various opaque contexts used internally as well as the per-file object contexts available through <b>FsRtl<i>Xxx</i></b> routines.

## -remarks
Drivers can use the <b>FsContext</b> and <b>FsContext2</b> members to maintain driver-determined state about an open file object. A driver cannot use these members unless the file object is accessible in the driver's I/O stack location of an IRP.

All remaining members in a file object are either opaque or read-only:

Opaque members within a file object should be considered inaccessible. Drivers with dependencies on object field locations or access to opaque members might not remain portable and interoperable with other drivers over time.

Drivers can use read-only members to acquire relevant information but must not modify read-only members and, if a pointer, the object that the member points to.

During the processing of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request, a file system driver calls the <a href="kernel.iosetshareaccess">IoSetShareAccess</a> routine (if the client is the first to open the file) or the <a href="kernel.iocheckshareaccess">IoCheckShareAccess</a> routine (for subsequent clients that want to share the file). <b>IoSetShareAccess</b> and <b>IoCheckShareAccess</b> update the <b>ReadAccess</b>, <b>WriteAccess</b>, and <b>DeleteAccess</b> members to indicate the access rights that are granted to the client if the client has exclusive access to the file. Additionally, <b>IoCheckShareAccess</b> updates the <b>SharedRead</b>, <b>SharedWrite</b>, and <b>SharedDelete</b> members to indicate the access rights that are simultaneously granted to two or more clients that share the file. If the driver for a device other than a file system has to monitor the access rights of clients, this driver typically stores access rights information in context buffers that are pointed to by the <b>FsContext</b> and <b>FsContext2</b> members.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="ifsk.the_fobx_structure">FOBX</a>
</dt>
<dt>
<a href="ifsk.fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>
</dt>
<dt>
<a href="kernel.iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>
</dt>
<dt>
<a href="kernel.iocheckshareaccess">IoCheckShareAccess</a>
</dt>
<dt>
<a href="kernel.iosetshareaccess">IoSetShareAccess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_OBJECT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
