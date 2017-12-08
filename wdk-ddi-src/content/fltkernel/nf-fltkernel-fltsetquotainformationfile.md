---
UID: NF.fltkernel.FltSetQuotaInformationFile
title: FltSetQuotaInformationFile function
author: windows-driver-content
description: The FltSetQuotaInformationFile routine modifies quota entries for a file object.
old-location: ifsk\fltsetquotainformationfile.htm
old-project: ifsk
ms.assetid: 89EC9F5C-24AE-4340-99CF-05323F99B465
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltSetQuotaInformationFile
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
req.alt-api: FltSetQuotaInformationFile
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

# FltSetQuotaInformationFile function



## -description
The <b>FltSetQuotaInformationFile</b> routine modifies quota entries for a file object. 


## -syntax

````
NTSTATUS FltSetQuotaInformationFile(
  _In_ PFLT_INSTANCE Instance,
  _In_ PFILE_OBJECT  FileObject,
  _In_ PVOID         Buffer,
  _In_ ULONG         Length
);
````


## -parameters

### -param Instance [in]

An opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides. 

### -param FileObject [in]

The file object pointer for the file. 

### -param Buffer [in]

A pointer to a caller-supplied, <a href="ifsk.file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>-structured input buffer that contains the quota information entries to be set. 

### -param Length [in]

The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to. 

## -returns
<b>FltSetQuotaInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following. 
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
<a href="ifsk.fltqueryquotainformationfile">FltQueryQuotaInformationFile</a>
</dt>
<dt>
<a href="kernel.zwsetquotainformationfile">ZwSetQuotaInformationFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetQuotaInformationFile function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
