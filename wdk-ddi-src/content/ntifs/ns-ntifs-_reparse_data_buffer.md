---
UID: NS.NTIFS._REPARSE_DATA_BUFFER
title: _REPARSE_DATA_BUFFER
author: windows-driver-content
description: The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point.
old-location: ifsk\reparse_data_buffer.htm
old-project: ifsk
ms.assetid: e906a874-51f1-4623-8f0b-afdfd8169ab2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _REPARSE_DATA_BUFFER, *PREPARSE_DATA_BUFFER, REPARSE_DATA_BUFFER
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
req.alt-api: REPARSE_DATA_BUFFER
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

# _REPARSE_DATA_BUFFER structure



## -description
The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point. (Third-party reparse point owners must use the <a href="ifsk.reparse_guid_data_buffer">REPARSE_GUID_DATA_BUFFER</a> structure instead.) 



## -syntax

````
typedef struct _REPARSE_DATA_BUFFER {
  ULONG  ReparseTag;
  USHORT ReparseDataLength;
  USHORT Reserved;
  union {
    struct {
      USHORT SubstituteNameOffset;
      USHORT SubstituteNameLength;
      USHORT PrintNameOffset;
      USHORT PrintNameLength;
      ULONG  Flags;
      WCHAR  PathBuffer[1];
    } SymbolicLinkReparseBuffer;
    struct {
      USHORT SubstituteNameOffset;
      USHORT SubstituteNameLength;
      USHORT PrintNameOffset;
      USHORT PrintNameLength;
      WCHAR  PathBuffer[1];
    } MountPointReparseBuffer;
    struct {
      UCHAR DataBuffer[1];
    } GenericReparseBuffer;
  };
} REPARSE_DATA_BUFFER, *PREPARSE_DATA_BUFFER;
````


## -struct-fields

### -field ReparseTag

Reparse point tag. Must be a Microsoft reparse point tag. (See the following <b>Remarks</b> section.) 


### -field ReparseDataLength

Size, in bytes, of the reparse data in the <b>DataBuffer</b> member. 


### -field Reserved

Length, in bytes, of the unparsed portion of the file name pointed to by the <b>FileName</b> member of the associated file object. For more information about the <b>FileName</b> member, see <a href="kernel.file_object">FILE_OBJECT</a>. This member is only valid for create operations when the I/O fails with STATUS_REPARSE. For all other purposes, such as setting or querying a reparse point for the reparse data, this member is treated as reserved.


### -field ( unnamed union )

 


### -field SymbolicLinkReparseBuffer


### -field SubstituteNameOffset

Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. 


### -field SubstituteNameLength

Length, in bytes, of the substitute name string. If this string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL character. 


### -field PrintNameOffset

Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. 


### -field PrintNameLength

Length, in bytes, of the print name string. If this string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL character. 


### -field Flags

Used to indicate if the given symbolic link is an absolute or relative symbolic link.  If <b>Flags</b> contains SYMLINK_FLAG_RELATIVE, the symbolic link contained in the <b>PathBuffer</b> array (at offset <b>SubstitueNameOffset</b>) is processed as a relative symbolic link; otherwise, it is processed as an absolute symbolic link.


### -field PathBuffer

First character of the path string. This is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the <b>PathBuffer</b>. (To locate the substitute name and print name strings in the <b>PathBuffer</b>, use the <b>SubstituteNameOffset</b>, <b>SubstituteNameLength</b>, <b>PrintNameOffset</b>, and <b>PrintNameLength</b> members.) 

</dd>
</dl>

### -field MountPointReparseBuffer


### -field SubstituteNameOffset

Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. 


### -field SubstituteNameLength

Length, in bytes, of the substitute name string. If this string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL character. 


### -field PrintNameOffset

Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. 


### -field PrintNameLength

Length, in bytes, of the print name string. If this string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL character. 


### -field PathBuffer

First character of the path string. This is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the <b>PathBuffer</b>. (To locate the substitute name and print name strings in the <b>PathBuffer</b>, use the <b>SubstituteNameOffset</b>, <b>SubstituteNameLength</b>, <b>PrintNameOffset</b>, and <b>PrintNameLength</b> members.) 

</dd>
</dl>

### -field GenericReparseBuffer


### -field DataBuffer

Microsoft-defined data for the reparse point. 

</dd>
</dl>
</dd>
</dl>

## -remarks
The REPARSE_DATA_BUFFER structure is used by Microsoft file systems, filters, and minifilter drivers, as well as the I/O manager, to store data for a reparse point. 

This structure can only be used for Microsoft reparse points. Third-party reparse point owners must use the <a href="ifsk.reparse_guid_data_buffer">REPARSE_GUID_DATA_BUFFER</a> structure instead. 

Microsoft reparse points can use the REPARSE_DATA_BUFFER structure or the REPARSE_GUID_DATA_BUFFER structure. 

For more information about reparse point tags, see the Microsoft Windows SDK documentation. 

For more information about absolute and relative symbolic links, see Creating Symbolic Links in the Microsoft Windows SDK documentation.


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
<a href="ifsk.file_reparse_point_information">FILE_REPARSE_POINT_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.flt_parameters_for_irp_mj_file_system_control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="ifsk.fltfscontrolfile">FltFsControlFile</a>
</dt>
<dt>
<a href="ifsk.flttagfile">FltTagFile</a>
</dt>
<dt>
<a href="ifsk.fltuntagfile">FltUntagFile</a>
</dt>
<dt>
<a href="ifsk.fsctl_delete_reparse_point">FSCTL_DELETE_REPARSE_POINT</a>
</dt>
<dt>
<a href="ifsk.fsctl_get_reparse_point">FSCTL_GET_REPARSE_POINT</a>
</dt>
<dt>
<a href="ifsk.fsctl_set_reparse_point">FSCTL_SET_REPARSE_POINT</a>
</dt>
<dt>
<a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="ifsk.isreparsetagmicrosoft">IsReparseTagMicrosoft</a>
</dt>
<dt>
<a href="ifsk.isreparsetagnamesurrogate">IsReparseTagNameSurrogate</a>
</dt>
<dt>
<a href="ifsk.reparse_guid_data_buffer">REPARSE_GUID_DATA_BUFFER</a>
</dt>
<dt>
<a href="kernel.zwfscontrolfile">ZwFsControlFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REPARSE_DATA_BUFFER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

