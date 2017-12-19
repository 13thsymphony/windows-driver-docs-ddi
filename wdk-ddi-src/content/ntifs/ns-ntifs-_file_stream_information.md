---
UID: NS.NTIFS._FILE_STREAM_INFORMATION
title: _FILE_STREAM_INFORMATION
author: windows-driver-content
description: The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file.
old-location: ifsk\file_stream_information.htm
old-project: ifsk
ms.assetid: 03472920-cb22-42e1-b0e5-488c0319fc03
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILE_STREAM_INFORMATION, *PFILE_STREAM_INFORMATION, PFILE_STREAM_INFORMATION, FILE_STREAM_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_STREAM_INFORMATION
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _FILE_STREAM_INFORMATION structure



## -description
The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file. 



## -syntax

````
typedef struct _FILE_STREAM_INFORMATION {
  ULONG         NextEntryOffset;
  ULONG         StreamNameLength;
  LARGE_INTEGER StreamSize;
  LARGE_INTEGER StreamAllocationSize;
  WCHAR         StreamName[1];
} FILE_STREAM_INFORMATION, *PFILE_STREAM_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

The offset of the next FILE_STREAM_INFORMATION entry. This member is zero if no other entries follow this one. 


### -field StreamNameLength

Length, in bytes, of the <b>StreamName</b> string. 


### -field StreamSize

Size, in bytes, of the stream. 


### -field StreamAllocationSize

File stream allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device. 


### -field StreamName

Unicode string that contains the name of the stream. 


## -remarks
The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file. This operation can be performed in either of the following ways: 

By calling <a href="ifsk.fltqueryinformationfile">FltQueryInformationFile</a> or <a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a> and specifying FileStreamInformation for the <i>FileInformationClass</i> parameter. On return, the <i>FileInformation</i> buffer contains a FILE_STREAM_INFORMATION structure for each file stream. 

By sending an IRP_MJ_QUERY_INFORMATION request to the file system and specifying FileStreamInformation for the <i>FileInformationClass</i> parameter. On return, <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a FILE_STREAM_INFORMATION structure for each file stream. 

No specific access rights are required to query this information. Thus this information is available as long as the file is open. 

Support for stream enumeration is file system-dependent. If a file system does not support stream enumeration, it should return STATUS_INVALID_PARAMETER or STATUS_NOT_IMPLEMENTED for these requests. 

If a file system supports stream enumeration, but the file has no streams other than the default data stream, which is unnamed, the file system should return a single FILE_STREAM_INFORMATION structure containing either "::$DATA" or a zero-length Unicode string as the <b>StreamName</b>. 

NTFS returns "::$DATA" as the <b>StreamName</b> for the default data stream. 

For a named data stream, NTFS appends ":$DATA" to the stream name. For example, for a user data stream with the name "Authors," NTFS returns ":Authors:$DATA" as the <b>StreamName</b>. 

When calling a routine such as <a href="kernel.zwcreatefile">ZwCreateFile</a> to open a named file stream, the ":$DATA" portion of the name can be omitted. For example, to open the "Authors" stream of a file named "Book," the caller can specify "Book:Authors" or "Book:Authors:$DATA" as the stream name. Both names are equivalent. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="ifsk.fltqueryinformationfile">FltQueryInformationFile</a> or <a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a> must be at least <b>sizeof</b> (FILE_STREAM_INFORMATION). If this buffer is not large enough to hold a FILE_STREAM_INFORMATION structure for each file stream, <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b> returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL. Because such an unsuccessful call to <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b> does not return the required buffer size, filter drivers must make one or more additional calls to <b>FltQueryInformationFile</b> or <b>ZwQueryInformationFile</b>, passing a larger buffer in each call, until the buffer is large enough. 

Support for named data streams is file-system-specific. File system filter drivers can determine whether a file system supports named streams in either of the following ways: 

By calling <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a> or <a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a> and specifying FileFsAttributeInformation for the <i>FsInformationClass</i> parameter. On return, the <i>FsInformation</i> buffer contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the <b>FileSystemAttributes</b> member of this structure, the file system supports named streams. 

By sending an IRP_MJ_QUERY_VOLUME_INFORMATION request to the file system and specifying FileFsAttributeInformation for the <i>FsInformationClass</i> parameter. On return, <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a FILE_FS_ATTRIBUTE_INFORMATION structure. If the FILE_NAMED_STREAMS bit is set in the <b>FileSystemAttributes</b> member of this structure, the file system supports named streams. 

The FILE_STREAM_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltqueryinformationfile">FltQueryInformationFile</a>
</dt>
<dt>
<a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_information">IRP_MJ_QUERY_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_volume_information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_STREAM_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
