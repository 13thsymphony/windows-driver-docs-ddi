---
UID: NF.ntifs.CcSetLogHandleForFile
title: CcSetLogHandleForFile function
author: windows-driver-content
description: The CcSetLogHandleForFile routine sets a log handle for a file.
old-location: ifsk\ccsetloghandleforfile.htm
old-project: ifsk
ms.assetid: 7bb56650-a75e-4b49-bfb3-83848ede29c0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: CcSetLogHandleForFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcSetLogHandleForFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
---

# CcSetLogHandleForFile function



## -description
The <b>CcSetLogHandleForFile</b> routine sets a log handle for a file. 



## -syntax

````
VOID CcSetLogHandleForFile(
  _In_ PFILE_OBJECT  FileObject,
  _In_ PVOID         LogHandle,
  _In_ PFLUSH_TO_LSN FlushToLsnRoutine
);
````


## -parameters

### -param FileObject [in]

Pointer to the file object for the file for which the log handle is to be stored. 


### -param LogHandle [in]

Pointer to the log handle that is to be stored. 


### -param FlushToLsnRoutine [in]

Pointer to a log file flush callback routine to call before flushing buffers for this file. This routine is called to ensure that a log file is flushed to the most recent logical sequence number (LSN) for any buffer control block (BCB) being flushed. This routine is declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PFLUSH_TO_LSN) (
            IN PVOID LogHandle,
            IN LARGE_INTEGER Lsn
            );</pre>
</td>
</tr>
</table></span></div>

### -param LogHandle

<dd>
Pointer to an opaque structure that is used to identify this client. 


### -param Lsn

<dd>
This is the LSN that must be on the disk on return from this callback routine. 

</dd>
</dl>

## -returns
None


## -remarks
<b>CcSetLogHandleForFile</b> sets a log handle for a file, for use in subsequent calls to <a href="ifsk.ccgetdirtypages">CcGetDirtyPages</a>. 


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
Available on Microsoft Windows XP and later. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccgetdirtypages">CcGetDirtyPages</a>
</dt>
<dt>
<a href="ifsk.ccsetdirtypinneddata">CcSetDirtyPinnedData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetLogHandleForFile routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

