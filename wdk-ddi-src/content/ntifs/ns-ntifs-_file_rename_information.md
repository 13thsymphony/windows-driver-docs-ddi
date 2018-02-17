---
UID: NS:ntifs._FILE_RENAME_INFORMATION
title: "_FILE_RENAME_INFORMATION"
author: windows-driver-content
description: The FILE_RENAME_INFORMATION structure is used to rename a file.
old-location: ifsk\file_rename_information.htm
old-project: ifsk
ms.assetid: 25a195ab-faf1-488d-a9b2-65ae88b57ebd
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fileinformationstructures_d9a99263-5aec-400a-ab30-73949a81a4f6.xml, FILE_RENAME_INFORMATION structure [Installable File System Drivers], FILE_RENAME_INFORMATION, _FILE_RENAME_INFORMATION, ifsk.file_rename_information, PFILE_RENAME_INFORMATION structure pointer [Installable File System Drivers], *PFILE_RENAME_INFORMATION, ntifs/PFILE_RENAME_INFORMATION, PFILE_RENAME_INFORMATION, ntifs/FILE_RENAME_INFORMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FILE_RENAME_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILE_RENAME_INFORMATION, FILE_RENAME_INFORMATION"
---

# _FILE_RENAME_INFORMATION structure
The <b>FILE_RENAME_INFORMATION</b> structure is used to rename a file.

## Syntax
````
typedef struct _FILE_RENAME_INFORMATION {
  BOOLEAN ReplaceIfExists;
  HANDLE  RootDirectory;
  ULONG   FileNameLength;
  WCHAR   FileName[1];
} FILE_RENAME_INFORMATION, *PFILE_RENAME_INFORMATION;
````

## Members


`DUMMYUNIONNAME`



`FileName`

The first character of a wide-character string containing the new name for the file. This is followed in memory by the remainder of the string. If the <b>RootDirectory</b> member is <b>NULL</b>, and the file is being moved to a different directory, this member specifies the full pathname to be assigned to the file. Otherwise, it specifies only the file name or a relative pathname.

`FileNameLength`

Length, in bytes, of the new name for the file.

`ReplaceIfExists`

Set to <b>TRUE</b> to specify that if a file with the given name already exists, it should be replaced with the given file. Set to <b>FALSE</b> if the rename operation should fail if a file with the given name already exists.

`RootDirectory`

If the file is not being moved to a different directory, or if the <b>FileName</b> member contains the full pathname, this member is <b>NULL</b>. Otherwise, it is a handle for the root directory under which the file will reside after it is renamed.

## Remarks
The <b>FILE_RENAME_INFORMATION</b> structure is used to rename a file. This operation can be performed in either of the following ways: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a> or <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, passing <b>FileRenameInformation</b> as the value of <i>FileInformationClass</i> and passing a caller-allocated buffer formatted as a <b>FILE_RENAME_INFORMATION</b> structure for the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the file to be renamed. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_INFORMATION. 

</li>
</ul>
File system minifilters must use <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>, not <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, to rename a file. 

Renaming a file requires DELETE access to the file so that the directory entry may be removed from the current parent directory, as well as the appropriate access to create the new entry in the new parent directory file. 

The file name string in the <b>FileName</b> member must be specified in one of the following forms. 

<ul>
<li>
A simple file name. (The <b>RootDirectory</b> member is <b>NULL</b>.) In this case, the file is simply renamed within the same directory. That is, the rename operation changes the name of the file but not its location. 

</li>
<li>
A fully qualified file name. (The <b>RootDirectory</b> member is <b>NULL</b>.) In this case, the rename operation changes the name and location of the file. 

</li>
<li>
A relative file name. In this case, the <b>RootDirectory</b> member contains a handle to the target directory for the rename operation. The file name itself must be a simple file name. 

</li>
</ul>
General rules for rename operations: 

<ul>
<li>
A file or directory can only be renamed within a volume. In other words, a rename operation cannot cause a file or directory to be moved to a different volume. 

</li>
<li>
A volume's root directory cannot be renamed. 

</li>
<li>
If <b>ReplaceIfExists</b> is set to <b>FALSE</b>, and the target exists, the rename operation will fail. 

</li>
<li>
Even if <b>ReplaceIfExists</b> is set to <b>TRUE</b>, the rename operation will still fail if a file with the same name already exists and is a directory, a read-only file, or a currently executing file. 

</li>
<li>
A volume's files and directories cannot be renamed if the volume is a read-only volume, such as a CDFS volume or a read-only NTFS volume. 

</li>
</ul>
Special rules for renaming open files: 

<ul>
<li>
A file cannot be renamed if it has any open handles, unless it is only open because of a batch opportunistic lock (oplock) and the batch oplock can be broken immediately. 

</li>
<li>
A file cannot be renamed if a file with the same name exists and has open handles (except in the batch-oplock case described earlier). 

</li>
<li>
A directory cannot be renamed if it or any of its subdirectories contains a file that has open handles (except in the batch-oplock case described earlier). 

</li>
</ul>
Special rules for renaming NTFS data streams: 

<ul>
<li>
The source handle cannot be opened with FILE_DIRECTORY_FILE. 

</li>
<li>
The source handle cannot be a directory opened without either FILE_DIRECTORY_FILE or FILE_NON_DIRECTORY_FILE. 

</li>
<li>
The new name for the stream must begin with a colon (:). 

</li>
<li>
A data stream can only be renamed within a file. In other words, a rename operation cannot cause a data stream to be moved to a different file. 

</li>
<li>
A stream on a directory cannot be renamed to the default data stream. 

</li>
<li>
If <b>ReplaceIfExists</b> is set to <b>TRUE</b>, the rename operation will succeed only if a stream with the same name exists and is a zero-length data stream. 

</li>
<li>
"Renaming" the default data stream is allowed, but this is not a true rename, because it leaves behind a zero-length default data stream. 

</li>
</ul>
The size of the <i>FileInformation</i> buffer passed to <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> or <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a> must be &gt;= <b>sizeof</b>(FILE_RENAME_INFORMATION) plus the size in bytes of the <b>FileName</b> string.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_RENAME_INFORMATION structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>