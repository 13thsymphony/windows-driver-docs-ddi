---
UID: NF.wdm.ClfsGetContainerName
title: ClfsGetContainerName
author: windows-driver-content
description: The ClfsGetContainerName routine returns the path name of a specified container.
old-location: kernel\clfsgetcontainername.htm
old-project: kernel
ms.assetid: 727b2e29-9e2d-4386-a30b-5727e1261fad
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ClfsGetContainerName
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
req.alt-api: ClfsGetContainerName
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
req.iface: 
req.product: Windows 10 or later.
---

# ClfsGetContainerName function



## -description
<p>The <b>ClfsGetContainerName</b> routine returns the path name of a specified container.</p>


## -syntax

````
NTSTATUS ClfsGetContainerName(
  _In_      PLOG_FILE_OBJECT  plfoLog,
  _In_      CLFS_CONTAINER_ID cidLogicalContainer,
  _Out_     PUNICODE_STRING   puszContainerName,
  _Out_opt_ PULONG            pcActualLenContainerName
);
````


## -parameters
<dl>

### -param <i>plfoLog</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.</p>
</dd>

### -param <i>cidLogicalContainer</i> [in]

<dd>
<p>The logical identifier of a container in the CLFS log.</p>
</dd>

### -param <i>puszContainerName</i> [out]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure. The <b>Buffer</b> member of <i>puszContainerName</i> must point to a caller-allocated buffer that receives the path name of the container. The <b>MaximumLength</b> member must supply the size of the buffer.</p>
</dd>

### -param <i>pcActualLenContainerName</i> [out, optional]

<dd>
<p>A pointer to a ULONG-typed variable that receives the actual length, in Unicode characters, of the container's path name. This parameter can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p><b>ClfsGetContainerName</b> returns one of the status codes defined in Ntstatus.h. The following table gives the meanings of various return values.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name.</p><dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><p>The actual length, in Unicode characters, of the full path name is larger than <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container truncated to the number of characters specified by <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name. </p><dl>
<dt><b>Other</b></dt>
</dl><p>On return, the contents of <i>puszContainerName</i>-&gt;<b>Buffer</b> and <i>pcActualLenContainerName</i> are undefined.</p>

<p> </p>

## -remarks
<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

<p>For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540768">ClfsAddLogContainer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541715">ClfsRemoveLogContainer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsGetContainerName routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
