---
UID: NS.NTIFS._FILE_FS_ATTRIBUTE_INFORMATION
title: _FILE_FS_ATTRIBUTE_INFORMATION
author: windows-driver-content
description: The FILE_FS_ATTRIBUTE_INFORMATION structure is used to query attribute information for a file system.
old-location: ifsk\file_fs_attribute_information.htm
old-project: ifsk
ms.assetid: 373788d8-4963-4319-82ae-3a0675c9fff4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILE_FS_ATTRIBUTE_INFORMATION, FILE_FS_ATTRIBUTE_INFORMATION, *PFILE_FS_ATTRIBUTE_INFORMATION
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
req.alt-api: FILE_FS_ATTRIBUTE_INFORMATION
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

# _FILE_FS_ATTRIBUTE_INFORMATION structure



## -description
The <b>FILE_FS_ATTRIBUTE_INFORMATION</b> 
   structure is used to query attribute information for a file system.



## -syntax

````
typedef struct _FILE_FS_ATTRIBUTE_INFORMATION {
  ULONG FileSystemAttributes;
  LONG  MaximumComponentNameLength;
  ULONG FileSystemNameLength;
  WCHAR FileSystemName[1];
} FILE_FS_ATTRIBUTE_INFORMATION, *PFILE_FS_ATTRIBUTE_INFORMATION;
````


## -struct-fields

### -field FileSystemAttributes

Bitmask of flags specifying attributes of the specified file system, as a compatible combination of the 
       following flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FILE_CASE_PRESERVED_NAMES</b>

</td>
<td>
The file system preserves the case of file names when it places a name on disk.

</td>
</tr>
<tr>
<td>
<b>FILE_CASE_SENSITIVE_SEARCH</b>

</td>
<td>
The file system supports case-sensitive file names.

</td>
</tr>
<tr>
<td>
<b>FILE_FILE_COMPRESSION</b>

</td>
<td>
The file system supports file-based compression. This flag is incompatible with the 
          <b>FILE_VOLUME_IS_COMPRESSED</b> flag.

</td>
</tr>
<tr>
<td>
<b>FILE_NAMED_STREAMS</b>

</td>
<td>
The file system supports named streams.

</td>
</tr>
<tr>
<td>
<b>FILE_PERSISTENT_ACLS</b>

</td>
<td>
The file system preserves and enforces access control lists 
          (<a href="ifsk.acl">ACL</a>).

</td>
</tr>
<tr>
<td>
<b>FILE_READ_ONLY_VOLUME</b>

</td>
<td>
<b>Microsoft Windows XP and later:</b> The specified volume is read-only.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_ENCRYPTION</b>

</td>
<td>
The file system supports the Encrypted File System (EFS).

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_OBJECT_IDS</b>

</td>
<td>
The file system supports object identifiers.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_REMOTE_STORAGE</b>

</td>
<td>
The file system supports remote storage.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_REPARSE_POINTS</b>

</td>
<td>
The file system supports reparse points.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_SPARSE_FILES</b>

</td>
<td>
The file system supports sparse files.

</td>
</tr>
<tr>
<td>
<b>FILE_UNICODE_ON_DISK</b>

</td>
<td>
The file system supports Unicode in file names.

</td>
</tr>
<tr>
<td>
<b>FILE_VOLUME_IS_COMPRESSED</b>

</td>
<td>
The specified volume is a compressed volume. This flag is incompatible with the 
          <b>FILE_FILE_COMPRESSION</b> flag.

</td>
</tr>
<tr>
<td>
<b>FILE_VOLUME_QUOTAS</b>

</td>
<td>
The file system supports per-user quotas.

</td>
</tr>
</table>
 


### -field MaximumComponentNameLength

Maximum file name component length, in bytes, supported by the specified file system. A file name component 
      is that portion of a file name between backslashes.


### -field FileSystemNameLength

Length, in bytes, of the file system name.


### -field FileSystemName

File system name.


## -remarks
This information can be queried in either of the following ways:

Call <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a> or 
       <a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a>, passing 
       <b>FileFsAttributeInformation</b> as the value of 
       <i>FileInformationClass</i> and passing a caller-allocated, 
       <b>FILE_FS_ATTRIBUTE_INFORMATION</b>-structured 
       buffer as the value of <i>FileInformation</i>.

On CSVFS <b>FileFsAttributeInformation</b> returns 
       <b>FILE_FS_ATTRIBUTE_INFORMATION</b> for the 
       CSVFS file system. If you want to query <b>FileFsAttributeInformation</b> for the file 
       system CSVFS is layered on then you should use 
       <a href="fs.fsctl_csv_query_down_level_file_system_characteristics">FSCTL_CSV_QUERY_DOWN_LEVEL_FILE_SYSTEM_CHARACTERISTICS</a>.

Create an IRP with major function code 
       <a href="ifsk.irp_mj_query_volume_information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>.

No specific access rights are required to query this information. Thus this information is available as long as 
     the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume.

The size of the buffer passed in the <i>FileInformation</i> parameter to 
     <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a> or 
     <a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a> must be at 
     least <code>sizeof(FILE_FS_ATTRIBUTE_INFORMATION)</code>.

This structure must be aligned on a <b>LONG</b> (4-byte) boundary.


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
<a href="ifsk.acl">ACL</a>
</dt>
<dt>
<a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_volume_information">IRP_MJ_QUERY_VOLUME_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwqueryvolumeinformationfile">ZwQueryVolumeInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_FS_ATTRIBUTE_INFORMATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

