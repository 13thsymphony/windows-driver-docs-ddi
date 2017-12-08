---
UID: NF.wdm.ClfsSetLogFileInformation
title: ClfsSetLogFileInformation function
author: windows-driver-content
description: The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log.
old-location: kernel\clfssetlogfileinformation.htm
old-project: kernel
ms.assetid: 9f44b1ce-25d4-438f-b4eb-cff7bbfb5e0a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ClfsSetLogFileInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsSetLogFileInformation
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# ClfsSetLogFileInformation function



## -description
The <b>ClfsSetLogFileInformation</b> routine sets metadata and state information for a specified stream and its underlying physical log.


## -syntax

````
NTSTATUS ClfsSetLogFileInformation(
  _In_ PLOG_FILE_OBJECT           plfoLog,
  _In_ CLFS_LOG_INFORMATION_CLASS eInformationClass,
  _In_ PVOID                      pinfoBuffer,
  _In_ ULONG                      cbBuffer
);
````


## -parameters

### -param plfoLog [in]

A pointer to a <a href="kernel.log_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="kernel.clfscreatelogfile">ClfsCreateLogFile</a>.

### -param eInformationClass [in]

A <a href="kernel.clfs_log_information_class">CLFS_LOG_INFORMATION_CLASS</a> value that specifies the class of information being set.

### -param pinfoBuffer [in]

A pointer to a buffer that supplies the log information. The structure of this buffer varies according to the class of information specified by <i>eInformationClass</i>. The following table shows the relationship between the information class and the buffer type.
<table>
<tr>
<th>Value of eInformationClass</th>
<th>Type of buffer pointed to by <i>pinfoBuffer</i></th>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformation</b>
</td>
<td>

<a href="kernel.clfs_information">CLFS_INFORMATION</a>

</td>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformationPhysical</b>
</td>
<td>

<a href="kernel.clfs_information">CLFS_INFORMATION</a>

</td>
</tr>
<tr>
<td>
<b>ClfsLogNameInformation</b>
</td>
<td>

<a href="kernel.clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>

</td>
</tr>
<tr>
<td>
<b>ClfsLogPhysicalNameInformation</b>
</td>
<td>

<a href="kernel.clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>

</td>
</tr>
<tr>
<td>
<b>ClfsLogStreamIdentifierInformation</b>
</td>
<td>

<a href="kernel.clfs_stream_id_information">CLFS_STREAM_ID_INFORMATION</a>

</td>
</tr>
</table>
 

### -param cbBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pinfoBuffer</i>.

## -returns
<b>ClfsSetLogFileInformation</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks
For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
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
<a href="kernel.clfs_information">CLFS_INFORMATION</a>
</dt>
<dt>
<a href="kernel.clfs_log_information_class">CLFS_LOG_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.clfs_stream_id_information">CLFS_STREAM_ID_INFORMATION</a>
</dt>
<dt>
<a href="kernel.log_file_object">LOG_FILE_OBJECT</a>
</dt>
<dt>
<a href="kernel.clfscreatelogfile">ClfsCreateLogFile</a>
</dt>
<dt>
<a href="kernel.clfsquerylogfileinformation">ClfsQueryLogFileInformation</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsSetLogFileInformation routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
