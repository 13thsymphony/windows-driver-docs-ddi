---
UID: NF:fltkernel.FltGetFileNameInformationUnsafe
title: FltGetFileNameInformationUnsafe function
author: windows-driver-content
description: The FltGetFileNameInformationUnsafe routine returns name information for an open file or directory.
old-location: ifsk\fltgetfilenameinformationunsafe.htm
old-project: ifsk
ms.assetid: 3c5ec515-d332-4fef-8b78-b2f04a672fd7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetFileNameInformationUnsafe
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
req.alt-api: FltGetFileNameInformationUnsafe
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
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltGetFileNameInformationUnsafe function



## -description
The <b>FltGetFileNameInformationUnsafe</b> routine returns name information for an open file or directory. 



## -syntax

````
NTSTATUS FltGetFileNameInformationUnsafe(
  _In_     PFILE_OBJECT               FileObject,
  _In_opt_ PFLT_INSTANCE              Instance,
  _In_     FLT_FILE_NAME_OPTIONS      NameOptions,
  _Out_    PFLT_FILE_NAME_INFORMATION *FileNameInformation
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the file or directory. The file object must be currently open. This parameter is required and cannot be set to <b>NULL</b>. 


### -param Instance [in, optional]

Instance pointer for the caller. This parameter can be set to <b>NULL</b>. 


### -param NameOptions [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a> value containing flags that specify the format of the name information to be returned, as well as the query method to be used by the Filter Manager. This parameter is required and cannot be set to <b>NULL</b>. 

The following table describes the name format flag values. Only one of the flags can be specified. For more information about these formats, see <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>. 

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
The <i>FileNameInformation</i> parameter receives the address of a structure containing the normalized name for the file. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_OPENED

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the name that was used when the file was opened. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_SHORT

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the short (8.3) name for the file. The short name consists of up to 8 characters, followed immediately by a period and up to 3 more characters. The short name for a file does not include the volume name, directory path, or stream name. 

</td>
</tr>
</table>
 

The following table describes the query method flag values. Only one of the flags can be specified. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_DEFAULT

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, <b>FltGetFileNameInformationUnsafe</b> queries the file system and caches the result. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_CACHE_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the file system. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the file system for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the Filter Manager's name cache, and does not cache the result of the file system query. 

</td>
</tr>
</table>
 


### -param FileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated FLT_FILE_NAME_INFORMATION structure. <b>FltGetFileNameInformationUnsafe</b> allocates this structure from paged pool. When this information is no longer needed, the caller must release the structure by calling <a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a>. This parameter is required and cannot be set to <b>NULL</b>. 


## -returns
<b>FltGetFileNameInformationUnsafe</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_INVALID_NAME_REQUEST</b></dt>
</dl>The file object that the <i>FileObject</i> parameter points to is not currently open. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid value was passed for the <i>FileNameInformation</i> parameter. This is an error code. 

 


## -remarks
The <b>FltGetFileNameInformationUnsafe</b> routine is provided so that you can query the name of a file object outside of the context of an I/O operation on that file object. In these cases, you must call <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>. 

Unlike the <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a> routine, <b>FltGetFileNameInformationUnsafe</b> does not protect the caller against the following types of circumstances, where querying the file system for name information can cause deadlocks: 

When the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>. For more information, see <a href="..\ntifs\nf-ntifs-iogettoplevelirp.md">IoGetTopLevelIrp</a>. 

In the paging I/O path. 

After an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a> operation is completed. 

In a postoperation callback routine for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION.

If a minifilter does not yet have a filter instance, such as in its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine, it can use <code>NULL</code> for the <i>Instance</i> parameter. This allows <i>DriverEntry</i> routines to access file name information. Except for this case, a <code>NULL</code> value for the instance parameter is reserved for system use.

In create, hard-link, and rename operations, file name tunneling can invalidate the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine. If a minifilter driver retrieves normalized file name information in a preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine by calling a routine such as <b>FltGetFileNameInformationUnsafe</b>, it must call <a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a> from its postoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine to retrieve the correct file name information for the file. 

For more information about normalized file name information, see <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>. 


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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreferencefilenameinformation.md">FltReferenceFileNameInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iogettoplevelirp.md">IoGetTopLevelIrp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetFileNameInformationUnsafe routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

