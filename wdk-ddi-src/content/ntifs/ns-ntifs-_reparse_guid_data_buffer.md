---
UID: NS.NTIFS._REPARSE_GUID_DATA_BUFFER
title: _REPARSE_GUID_DATA_BUFFER
author: windows-driver-content
description: The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.
old-location: ifsk\reparse_guid_data_buffer.htm
old-project: ifsk
ms.assetid: 9acb3b65-46c7-4b29-8d7a-c5d8fcd4563d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _REPARSE_GUID_DATA_BUFFER, REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER
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
req.alt-api: REPARSE_GUID_DATA_BUFFER
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

# _REPARSE_GUID_DATA_BUFFER structure



## -description
The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point. 



## -syntax

````
typedef struct _REPARSE_GUID_DATA_BUFFER {
  ULONG  ReparseTag;
  USHORT ReparseDataLength;
  USHORT Reserved;
  GUID   ReparseGuid;
  struct {
    UCHAR DataBuffer[1];
  } GenericReparseBuffer;
} REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER;
````


## -struct-fields

### -field ReparseTag

Reparse point tag that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


### -field ReparseDataLength

Size, in bytes, of the reparse data in the <b>DataBuffer</b> member. 


### -field Reserved

Reserved; do not use. 


### -field ReparseGuid

GUID that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


### -field GenericReparseBuffer


### -field DataBuffer

User-defined data for the reparse point. The format of this data is defined by the owner of the reparse point. 

</dd>
</dl>

## -remarks
The REPARSE_GUID_DATA_BUFFER structure is used by all third-party file systems, filters, and minifilters, as well as some Microsoft file systems, filters, and minifilters to store data for a reparse point. Each reparse point contains one REPARSE_GUID_DATA_BUFFER structure. 

Microsoft reparse points can use the <a href="ifsk.reparse_data_buffer">REPARSE_DATA_BUFFER</a> structure instead of the REPARSE_GUID_DATA_BUFFER structure. However, third-party reparse points are required to use the REPARSE_GUID_DATA_BUFFER structure. 

Reparse point tags are assigned to third parties by Microsoft. You may request more than one reparse point for use with a file system, file system filter driver, or minifilter driver. For more information about requesting a reparse point tag from Microsoft, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=8706">Windows IFS Kit</a> website. 

Reparse point GUIDs are not assigned by Microsoft. However, you must choose one GUID to use with your assigned reparse point tag, and you must always use this GUID with the tag. To generate a GUID, you should use GUIDGen (<i>Guidgen.exe</i>), a tool that is included in the Microsoft Windows SDK. 

Minifilters can set or delete a reparse point by calling <a href="ifsk.flttagfile">FltTagFile</a> or <a href="ifsk.fltuntagfile">FltUntagFile</a>. Minifilters can retrieve a reparse point by using the <a href="ifsk.fsctl_get_reparse_point">FSCTL_GET_REPARSE_POINT</a> control code. This code can be sent to the file system by calling <a href="ifsk.fltfscontrolfile">FltFsControlFile</a>. 

File systems and filter drivers can retrieve, set, or delete a reparse point by using the <a href="ifsk.fsctl_get_reparse_point">FSCTL_GET_REPARSE_POINT</a>, <a href="ifsk.fsctl_set_reparse_point">FSCTL_SET_REPARSE_POINT</a>, and <a href="ifsk.fsctl_delete_reparse_point">FSCTL_DELETE_REPARSE_POINT</a> control codes. These codes can be sent to the file system by calling <a href="kernel.zwfscontrolfile">ZwFsControlFile</a>. 

For more information about reparse points and reparse point tags, see the Windows SDK documentation.  


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
<a href="ifsk.reparse_data_buffer">REPARSE_DATA_BUFFER</a>
</dt>
<dt>
<a href="kernel.zwfscontrolfile">ZwFsControlFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REPARSE_GUID_DATA_BUFFER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

