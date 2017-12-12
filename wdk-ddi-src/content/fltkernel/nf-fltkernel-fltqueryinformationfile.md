---
UID: NF.fltkernel.FltQueryInformationFile
title: FltQueryInformationFile function
author: windows-driver-content
description: FltQueryInformationFile retrieves information for a given file.
old-location: ifsk\fltqueryinformationfile.htm
old-project: ifsk
ms.assetid: f80750fb-4561-4617-bc54-1360b2e93a68
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltQueryInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltQueryInformationFile
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL (see Remarks section)
---

# FltQueryInformationFile function



## -description
<b>FltQueryInformationFile</b> retrieves information for a given file. 



## -syntax

````
NTSTATUS FltQueryInformationFile(
  _In_      PFLT_INSTANCE          Instance,
  _In_      PFILE_OBJECT           FileObject,
  _Out_     PVOID                  FileInformation,
  _In_      ULONG                  Length,
  _In_      FILE_INFORMATION_CLASS FileInformationClass,
  _Out_opt_ PULONG                 LengthReturned
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param FileInformation [out]

Pointer to a caller-allocated buffer that receives information about the file. The <i>FileInformationClass</i> parameter specifies the type of information. This parameter is required and cannot be <b>NULL</b>. 


### -param Length [in]

Size, in bytes, of the <i>FileInformation</i> buffer. 


### -param FileInformationClass [in]

Type of file information to be returned. One of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileAllInformation</b>

</td>
<td>
Return a FILE_ALL_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileAttributeTagInformation</b>

</td>
<td>
Return a <a href="kernel.file_attribute_tag_information">FILE_ATTRIBUTE_TAG_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
Return a <a href="kernel.file_basic_information">FILE_BASIC_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileCompressionInformation</b>

</td>
<td>
Return a FILE_COMPRESSION_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileEaInformation</b>

</td>
<td>
Return a FILE_EA_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileInternalInformation</b>

</td>
<td>
Return a <a href="ifsk.file_internal_information">FILE_INTERNAL_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileMoveClusterInformation</b>

</td>
<td>
Return a FILE_MOVE_CLUSTER_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileNameInformation</b>

</td>
<td>
Return a <a href="kernel.file_name_information">FILE_NAME_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileNetworkOpenInformation</b>

</td>
<td>
Return a single <a href="kernel.file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Return a single <a href="kernel.file_position_information">FILE_POSITION_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileStandardInformation</b>

</td>
<td>
Return a single <a href="kernel.file_standard_information">FILE_STANDARD_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileStreamInformation</b>

</td>
<td>
Return a single <a href="ifsk.file_stream_information">FILE_STREAM_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileHardLinkInformation</b>

</td>
<td>
Return a <a href="ifsk.file_links_information">FILE_LINKS_INFORMATION</a> structure for the file. 

</td>
</tr>
</table>
 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the <i>FileInformation</i> buffer. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FltQueryInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>The file resides on a volume that is not currently mounted. This is an error code. 

 


## -remarks
A minifilter driver calls <b>FltQueryInformationFile</b> to retrieve information for a given file. The file must currently be open. 

<b>FltQueryInformationFile</b> returns zero in any member of a FILE_<i>XXX</i>_INFORMATION structure that is not supported by a particular file system. 

Callers of <b>FltQueryInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with APCs enabled</a>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.file_alignment_information">FILE_ALIGNMENT_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_attribute_tag_information">FILE_ATTRIBUTE_TAG_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_basic_information">FILE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_internal_information">FILE_INTERNAL_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_name_information">FILE_NAME_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_position_information">FILE_POSITION_INFORMATION</a>
</dt>
<dt>
<a href="kernel.file_standard_information">FILE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_stream_information">FILE_STREAM_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_links_information">FILE_LINKS_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.fltqueryvolumeinformationfile">FltQueryVolumeInformationFile</a>
</dt>
<dt>
<a href="ifsk.fltsetinformationfile">FltSetInformationFile</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryInformationFile function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

