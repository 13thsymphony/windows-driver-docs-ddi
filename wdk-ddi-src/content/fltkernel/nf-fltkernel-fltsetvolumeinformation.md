---
UID: NF.fltkernel.FltSetVolumeInformation
title: FltSetVolumeInformation function
author: windows-driver-content
description: FltSetVolumeInformation changes various kinds of information about the volume that the given instance is attached to.
old-location: ifsk\fltsetvolumeinformation.htm
old-project: ifsk
ms.assetid: ee6b4a41-e4a7-41b8-9ca9-77b9052724a3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltSetVolumeInformation
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
req.alt-api: FltSetVolumeInformation
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
req.irql: PASSIVE_LEVEL
---

# FltSetVolumeInformation function



## -description
<b>FltSetVolumeInformation</b> changes various kinds of information about the volume that the given instance is attached to. 


## -syntax

````
NTSTATUS FltSetVolumeInformation(
  _In_  PFLT_INSTANCE        Instance,
  _Out_ PIO_STATUS_BLOCK     Iosb,
  _Out_ PVOID                FsInformation,
  _In_  ULONG                Length,
  _In_  FS_INFORMATION_CLASS FsInformationClass
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for a minifilter driver instance that is attached to the volume. 

### -param Iosb [out]

Pointer to an IO_STATUS_BLOCK structure that receives the final completion status and information about the operation. 

### -param FsInformation [out]

Pointer to a caller-allocated buffer containing the values to be set for the volume. The structure of the information contained in the buffer is defined by the <i>FsInformationClass</i> parameter. 

### -param Length [in]

Size in bytes of the buffer that <i>FsInformation </i>points to. The caller should set this parameter according to the given <i>FsInformationClass</i>. For example, if the value of <i>FsInformationClass</i> is FileFsControlInformation, <i>Length</i> must be at least <b>sizeof(</b>FILE_FS_CONTROL_INFORMATION<b>)</b>. 

### -param FsInformationClass [in]

Type of information to be set for the volume. One of the following. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileFsControlInformation</b>
</td>
<td>
Set <a href="ifsk.file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a> for the volume. 
</td>
</tr>
<tr>
<td>
<b>FileFsLabelInformation</b>
</td>
<td>
Set <a href="ifsk.file_fs_label_information">FILE_FS_LABEL_INFORMATION</a> for the volume. 
</td>
</tr>
<tr>
<td>
<b>FileFsObjectIdInformation</b>
</td>
<td>
Set <a href="ifsk.file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a> for the volume. 
</td>
</tr>
</table>
 

## -returns
<b>FltSetVolumeInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>An invalid value was specified for <i>Length</i>. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltSetVolumeInformation</b> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>An invalid value was specified for <i>FsInformationClass</i>. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Instance</i> is attached to a network volume. <b>FltSetVolumeInformation</b> cannot be used to set network volume information. This is an error code. 

 

## -remarks
To query information about a volume, call <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>. 

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
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_fs_label_information">FILE_FS_LABEL_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetVolumeInformation function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
