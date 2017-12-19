---
UID: NS.NTIFS._FILE_LINK_INFORMATION
title: _FILE_LINK_INFORMATION
author: windows-driver-content
description: The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file.
old-location: ifsk\file_link_information.htm
old-project: ifsk
ms.assetid: c0c47dc7-d672-4094-af17-9de2b01886aa
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILE_LINK_INFORMATION, FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION, PFILE_LINK_INFORMATION
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
req.alt-api: FILE_LINK_INFORMATION
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

# _FILE_LINK_INFORMATION structure



## -description
The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. 



## -syntax

````
typedef struct _FILE_LINK_INFORMATION {
  BOOLEAN ReplaceIfExists;
  HANDLE  RootDirectory;
  ULONG   FileNameLength;
  WCHAR   FileName[1];
} FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION;
````


## -struct-fields

### -field ReplaceIfExists

Set to <b>TRUE</b> to specify that if the link already exists, it should be replaced with the new link. Set to <b>FALSE</b> if the link creation operation should fail if the link already exists. 


### -field RootDirectory

If the link is to be created in the same directory as the file that is being linked to, or if the <b>FileName</b> member contains the full pathname for the link to be created, this is <b>NULL</b>. Otherwise it is a handle for the directory where the link is to be created. 


### -field FileNameLength

Length, in bytes, of the file name string. 


### -field FileName

The first character of the name to be assigned to the newly created link. This is followed in memory by the remainder of the string. If the <b>RootDirectory</b> member is <b>NULL</b> and the link is to be created in a different directory from the file that is being linked to, this member specifies the full pathname for the link to be created. Otherwise, it specifies only the file name. (See the Remarks section for <a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a> for details on the syntax of this file name string.) 


## -remarks
The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. This operation can be performed in either of the following ways: 

Call <a href="ifsk.fltsetinformationfile">FltSetInformationFile</a> or <a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>, passing FileLinkInformation as the value of FileInformationClass and passing a caller-allocated, FILE_LINK_INFORMATION-structured buffer as the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the existing file to which the hard link should point. 

Create an IRP with major function code IRP_MJ_SET_INFORMATION. 

No specific access rights are required to set this information. 

File system minifilters must use <a href="ifsk.fltsetinformationfile">FltSetInformationFile</a>, not <a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>, to set this information for a file. 

For more information about NTFS hard links, see the Microsoft Windows SDK documentation for the Win32 <b>CreateHardLink</b> function. 

The size of the <i>FileInformation</i> buffer passed to <a href="ifsk.fltsetinformationfile">FltSetInformationFile</a> or <a href="kernel.zwsetinformationfile">ZwSetInformationFile</a> must be at least <b>sizeof</b>(FILE_LINK_INFORMATION). 

This structure must be aligned on a LONG (4-byte) boundary. 


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
<a href="ifsk.fltsetinformationfile">FltSetInformationFile</a>
</dt>
<dt>
<a href="ifsk.irp_mj_set_information">IRP_MJ_SET_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LINK_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

