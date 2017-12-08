---
UID: NF.fltkernel.FltUninitializeFileLock
title: FltUninitializeFileLock function
author: windows-driver-content
description: The FltUninitializeFileLock routine uninitializes a FILE_LOCK structure.
old-location: ifsk\fltuninitializefilelock.htm
old-project: ifsk
ms.assetid: 15f0a4f4-70f3-4a26-92a2-728e363205f3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltUninitializeFileLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltUninitializeFileLock
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
---

# FltUninitializeFileLock function



## -description
The <b>FltUninitializeFileLock</b> routine uninitializes a FILE_LOCK structure.


## -syntax

````
VOID FltUninitializeFileLock(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a> or <a href="ifsk.fltinitializefilelock">FltInitializeFileLock</a>.

## -returns
None

## -remarks
<b>FltUninitializeFileLock</b> uninitializes an initialized FILE_LOCK structure, freeing all file locks and completing any outstanding lock operations. The uninitialized FILE_LOCK structure can be initialized for reuse by a subsequent call to <a href="ifsk.fltinitializefilelock">FltInitializeFileLock</a>.

<b>FltUninitializeFileLock</b> can be used to uninitialize a FILE_LOCK structure allocated by a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. Do not use <b>FltUninitializeFileLock</b> for such a FILE_LOCK structure unless the structure is to be initialized for reuse. It is a programming error to call <a href="ifsk.fltfreefilelock">FltFreeFileLock</a> for an uninitialized FILE_LOCK structure.

To allocate and initialize a new file lock structure, call <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. 

To free an initialized FILE_LOCK structure, call <a href="ifsk.fltfreefilelock">FltFreeFileLock</a>. 

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
This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later. 
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
<a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>
</dt>
<dt>
<a href="ifsk.fltchecklockforreadaccess">FltCheckLockForReadAccess</a>
</dt>
<dt>
<a href="ifsk.fltchecklockforwriteaccess">FltCheckLockForWriteAccess</a>
</dt>
<dt>
<a href="ifsk.fltfreefilelock">FltFreeFileLock</a>
</dt>
<dt>
<a href="ifsk.fltinitializefilelock">FltInitializeFileLock</a>
</dt>
<dt>
<a href="ifsk.fltprocessfilelock">FltProcessFileLock</a>
</dt>
<dt>
<a href="ifsk.fsrtluninitializefilelock">FsRtlUninitializeFileLock</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltUninitializeFileLock routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
