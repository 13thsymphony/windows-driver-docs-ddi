---
UID: NF.wdm.ClfsCloseAndResetLogFile
title: ClfsCloseAndResetLogFile function
author: windows-driver-content
description: The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset.
old-location: kernel\clfscloseandresetlogfile.htm
old-project: kernel
ms.assetid: 5b52a012-1e3e-4d1f-8780-a7015b2f3c5f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ClfsCloseAndResetLogFile
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
req.alt-api: ClfsCloseAndResetLogFile
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

# ClfsCloseAndResetLogFile function



## -description
The <b>ClfsCloseAndResetLogFile</b> routine releases all references to a specified log file object and marks its associated stream for reset.



## -syntax

````
NTSTATUS ClfsCloseAndResetLogFile(
  _In_ PLOG_FILE_OBJECT plfoLog
);
````


## -parameters

### -param plfoLog [in]

A pointer to a <a href="kernel.log_file_object">LOG_FILE_OBJECT</a> structure for which references will be released. The caller previously obtained this pointer by calling <a href="kernel.clfscreatelogfile">ClfsCreateLogFile</a>.


## -returns
<b>ClfsCloseAndResetLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
<b>ClfsCloseAndResetLogFile</b> releases all references, acquired by CLFS, to the specified log file object. Typically, the client will not have acquired any additional references to the log file object. However, if the client has obtained additional refereces, it is the client's responsibility to release them.

<b>ClfsCloseAndResetLogFile</b> causes the specified log file object's reference count to drop to zero, at which time the log file object is closed (that is, its memory is deallocated). The stream represented by the log file object might not be reset, however, because there could be other log file objects that represent the same stream. The stream is reset after all log file objects that represent the stream are closed (for example by calls to <a href="kernel.clfscloselogfileobject">ClfsCloseLogFileObject</a>).

A reset stream is like a newly created stream that has never had any records written to it.

On return from this routine, <i>plfoLog</i> is invalid.

You can call <b>ClfsCloseAndResetLogFile</b> at most 124 times for a given stream.

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
<a href="kernel.clfscloselogfileobject">ClfsCloseLogFileObject</a>
</dt>
<dt>
<a href="kernel.clfsdeletelogbypointer">ClfsDeleteLogByPointer</a>
</dt>
<dt>
<a href="kernel.clfsdeletelogfile">ClfsDeleteLogFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsCloseAndResetLogFile routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

