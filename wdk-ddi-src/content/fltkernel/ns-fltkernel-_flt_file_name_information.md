---
UID: NS.FLTKERNEL._FLT_FILE_NAME_INFORMATION
title: _FLT_FILE_NAME_INFORMATION
author: windows-driver-content
description: The FLT_FILE_NAME_INFORMATION structure contains file name information.
old-location: ifsk\flt_file_name_information.htm
old-project: ifsk
ms.assetid: 998a028a-7dd8-429a-8195-68d4b4b1b156
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FLT_FILE_NAME_INFORMATION, *PFLT_FILE_NAME_INFORMATION, FLT_FILE_NAME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FLT_FILE_NAME_INFORMATION
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _FLT_FILE_NAME_INFORMATION structure



## -description
The FLT_FILE_NAME_INFORMATION structure contains file name information. 



## -syntax

````
typedef struct _FLT_FILE_NAME_INFORMATION {
  USHORT                     Size;
  FLT_FILE_NAME_PARSED_FLAGS NamesParsed;
  FLT_FILE_NAME_OPTIONS      Format;
  UNICODE_STRING             Name;
  UNICODE_STRING             Volume;
  UNICODE_STRING             Share;
  UNICODE_STRING             Extension;
  UNICODE_STRING             Stream;
  UNICODE_STRING             FinalComponent;
  UNICODE_STRING             ParentDir;
} FLT_FILE_NAME_INFORMATION, *PFLT_FILE_NAME_INFORMATION;
````


## -struct-fields

### -field Size

Size, in bytes, of the FLT_FILE_NAME_INFORMATION structure. 


### -field NamesParsed

Bitmask of flags that indicate which name components have been parsed from the <b>Name</b> string by <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a>. Note that, when parsing the <b>Name</b> string, <b>FltParseFileNameInformation</b> sets this flag for each component, whether the component is found to be present in the string. These values may be combined by using the OR operator. 

<table>
<tr>
<th>Flag</th>
<th>Component</th>
</tr>
<tr>
<td>
FLTFL_FILE_NAME_PARSED_FINAL_COMPONENT

</td>
<td>
<b>FinalComponent</b>

</td>
</tr>
<tr>
<td>
FLTFL_FILE_NAME_PARSED_EXTENSION

</td>
<td>
<b>Extension</b>

</td>
</tr>
<tr>
<td>
FLTFL_FILE_NAME_PARSED_STREAM

</td>
<td>
<b>Stream</b>

</td>
</tr>
<tr>
<td>
FLTFL_FILE_NAME_PARSED_PARENT_DIR

</td>
<td>
<b>ParentDir</b>

</td>
</tr>
</table>
 


### -field Format

Format of the name information stored in the <b>Name</b> member. One of the following. (For an explanation of these formats, see the following Remarks section.) 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_NORMALIZED

</td>
<td>
The <b>Name</b> member contains the normalized name for the file. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_OPENED

</td>
<td>
The <b>Name</b> member contains the name that was used when the file was opened. This name string is not normalized. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_SHORT

</td>
<td>
The <b>Name</b> member contains the short (8.3) name for the file. The short name for a file does not include the volume name, directory path, or stream name. This name string is not normalized. 

</td>
</tr>
</table>
 


### -field Name


<a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains the file name string, formatted as specified by the <b>Format</b> member. 


### -field Volume

UNICODE_STRING structure that contains the volume name parsed from the <b>Name</b> string. If <b>Format</b> is FLT_FILE_NAME_SHORT, <b>Volume.Length</b> is zero. 


### -field Share

UNICODE_STRING structure that contains the network share name parsed from the <b>Name</b> string for a remote file. If <b>Format</b> is FLT_FILE_NAME_SHORT, <b>Share.Length</b> is zero. 


### -field Extension

UNICODE_STRING structure that contains the extension parsed from the <b>Name</b> string. If no extension is found, <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a> sets <b>Extension.Length</b> to zero. 


### -field Stream

UNICODE_STRING structure that contains the stream name parsed from the <b>Name</b> string. If no stream name is found, or if <b>Format</b> is FLT_FILE_NAME_SHORT, <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a> sets <b>Stream.Length</b> to zero. 


### -field FinalComponent

UNICODE_STRING structure that contains the final name component parsed from the <b>Name</b> string. If no final component name is found, or if <b>Format</b> is FLT_FILE_NAME_SHORT, <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a> sets <b>FinalComponent.Length</b> to zero. 


### -field ParentDir

UNICODE_STRING structure that contains the parent directory name parsed from the <b>Name</b> string by <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a>. If no parent directory name is found, or if <b>Format</b> is FLT_FILE_NAME_SHORT, <b>FltParseFileNameInformation</b> sets <b>ParentDir.Length</b> to zero. 


## -remarks
The <b>Name</b> member contains one of the following: 

The normalized name for the file 

The opened name for the file 

The short name for the file 

A file name is considered <i>normalized</i> if all of the following are true: 

It contains the full directory path for the file, including the volume name, unless the user opened the file by file ID but does not have traverse privilege for the entire path. (For more information, see <a href="ifsk.fltgetfilenameinformation">FltGetFileNameInformation</a>.) 

The volume name is the volume's nonpersistent device object name (for example, "\Device\HarddiskVolume1"). 

All short names are expanded to the equivalent long names. 

Any trailing ":$DATA" or "::$DATA" strings are removed from the stream name. 

All mount points are resolved. 

The following is an example of a normalized file name for a local file: 

The following is an example of a normalized file name for a remote file: 

The <i>opened name</i> for a file is the name that was used when the file was opened. Like the normalized name, it contains the full directory path for the file, including the volume name. It differs from the normalized name in the following ways: 

The directory path for the file can contain short names as well as long names. 

Trailing ":$DATA" and "::$DATA" strings are not removed from the stream name. 

Mount points are not resolved. 

The following is an example of an opened file name for a local file: 

The following is an example of an opened file name for a remote file: 

The <i>short name</i> for a file is the short (8.3) name for the final component of the file name. Because it is generated when the file is opened, the short name is not available for an unopened file object, and it is not available in the create dispatch ("pre-create") path. It is also not available for NTFS stream file objects. Not all open files have short file names. For example, on NTFS partitions where short file name generation has been disabled, no files have short file names. 

The following is an example of a short name for a file: 

To obtain an FLT_FILE_NAME_INFORMATION structure for a file, call <a href="ifsk.fltgetfilenameinformation">FltGetFileNameInformation</a>, <a href="ifsk.fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>, or <a href="ifsk.fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>. These routines returns a pointer to a Filter Manager-owned FLT_FILE_NAME_INFORMATION structure that is shared by all minifilters. 

File systems such as NTFS and FAT use a per-volume tunnel cache to briefly preserve file names and other metadata for files that are being renamed, linked to, or deleted. This file name tunneling can cause the final component in normalized file name information returned by a preoperation call to <a href="ifsk.fltgetfilenameinformation">FltGetFileNameInformation</a>, <a href="ifsk.fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>, or <a href="ifsk.fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a> to be invalidated. If a minifilter retrieves normalized file name information in the preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine for a create, hard-link, or rename operation, it must call <a href="ifsk.fltgettunneledname">FltGetTunneledName</a> from its postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine to retrieve the correct file name information for the file. 

Although it contains numerous <a href="kernel.unicode_string">UNICODE_STRING</a> structures, the FLT_FILE_NAME_INFORMATION structure does not occupy much space in memory because all of the UNICODE_STRING structures in a FLT_FILE_NAME_INFORMATION structure share a single buffer. 

To parse the contents of the <b>Name</b> string, call <a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a>. This routine sets the values of the <b>Extension</b>, <b>Stream</b>, <b>FinalComponent</b>, <b>ParentDir</b>, and <b>NamesParsed</b> members of this structure. 

Minifilters are responsible for calling <a href="ifsk.fltreleasefilenameinformation">FltReleaseFileNameInformation</a> to release the FLT_FILE_NAME_INFORMATION structure when it is no longer needed. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_file_name_options">FLT_FILE_NAME_OPTIONS</a>
</dt>
<dt>
<a href="ifsk.fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>
</dt>
<dt>
<a href="ifsk.fltgetfilenameinformation">FltGetFileNameInformation</a>
</dt>
<dt>
<a href="ifsk.fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>
</dt>
<dt>
<a href="ifsk.fltgettunneledname">FltGetTunneledName</a>
</dt>
<dt>
<a href="ifsk.fltparsefilename">FltParseFileName</a>
</dt>
<dt>
<a href="ifsk.fltparsefilenameinformation">FltParseFileNameInformation</a>
</dt>
<dt>
<a href="ifsk.fltreferencefilenameinformation">FltReferenceFileNameInformation</a>
</dt>
<dt>
<a href="ifsk.fltreleasefilenameinformation">FltReleaseFileNameInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_FILE_NAME_INFORMATION structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

