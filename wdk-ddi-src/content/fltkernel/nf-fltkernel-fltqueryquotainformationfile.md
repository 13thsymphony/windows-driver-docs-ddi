---
UID: NF.fltkernel.FltQueryQuotaInformationFile
title: FltQueryQuotaInformationFile function
author: windows-driver-content
description: The FltQueryQuotaInformationFile routine retrieves quota entries associated with a file object.
old-location: ifsk\fltqueryquotainformationfile.htm
old-project: ifsk
ms.assetid: B460BE83-7050-469A-9AD6-68A47F03EB4B
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltQueryQuotaInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltQueryQuotaInformationFile
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

# FltQueryQuotaInformationFile function



## -description
The <b>FltQueryQuotaInformationFile</b> routine retrieves quota entries associated with a file object.



## -syntax

````
NTSTATUS FltQueryQuotaInformationFile(
  _In_      PFLT_INSTANCE    Instance,
  _In_      PFILE_OBJECT     FileObject,
  _Out_     PIO_STATUS_BLOCK IoStatusBlock,
  _Out_     PVOID            Buffer,
  _In_      ULONG            Length,
  _In_      BOOLEAN          ReturnSingleEntry,
  _In_opt_  PVOID            SidList,
  _In_      ULONG            SidListLength,
  _In_opt_  PULONG           StartSid,
  _In_      BOOLEAN          RestartScan,
  _Out_opt_ PULONG           LengthReturned
);
````


## -parameters

### -param Instance [in]

An opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

A file object pointer for an open file, directory, storage device, or volume. This parameter is required and cannot be <b>NULL</b>. 


### -param IoStatusBlock [out]

A caller-supplied <b>IO_STATUS_BLOCK</b> to receive the result of the call to <b>FltQueryQuotaInformationFile</b>. If the call  fails because of an invalid <b>SID</b> list, the <b>Information</b> field will contain the location in <i>SidList</i> where the error occurred.


### -param Buffer [out]

A pointer to a caller-supplied <a href="ifsk.file_get_ea_information"> FILE_GET_QUOTA_INFORMATION</a>-structured input buffer where the quota information values are to be returned. 


### -param Length [in]

The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to. 


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if <b>FltQueryQuotaInformationFile</b> should return only the first entry that is found. 


### -param SidList [in, optional]

A pointer to a caller-supplied <a href="ifsk.file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>-structured input buffer that specifies the quota information to be queried. This parameter is optional and can be <b>NULL</b>. 


### -param SidListLength [in]

The length, in bytes, of the buffer that the <i>SidList</i> parameter points to. 


### -param StartSid [in, optional]

The index of the entry at which to begin scanning the file's quota information list. This parameter is ignored if the <i>SidList</i> parameter points to a nonempty list. This parameter is optional and can be <b>NULL</b>. 


### -param RestartScan [in]

Set to <b>TRUE</b> if <b>FltQueryQuotaInformationFile</b> should begin the scan at the first entry in the file's quota information list. If this parameter is not set to <b>TRUE</b>, the scan is resumed from a previous call to <b>FltQueryQuotaInformationFile</b>. 


### -param LengthReturned [out, optional]

A pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in <i>Buffer</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FltQueryQuotaInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following. 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The instance or volume is being torn down. This is an error code. 

 


## -remarks


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
Version

</th>
<td width="70%">
Available starting with  Windows 8.

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
<a href="ifsk.file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.fltsetquotainformationfile">FltSetQuotaInformationFile</a>
</dt>
<dt>
<a href="kernel.zwqueryquotainformationfile">ZwQueryQuotaInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryQuotaInformationFile function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

