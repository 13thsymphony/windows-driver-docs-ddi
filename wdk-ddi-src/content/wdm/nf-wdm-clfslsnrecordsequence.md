---
UID: NF.wdm.ClfsLsnRecordSequence
title: ClfsLsnRecordSequence
author: windows-driver-content
description: The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
old-location: kernel\clfslsnrecordsequence.htm
old-project: kernel
ms.assetid: 407675de-4a06-49f7-9b43-c48b4c84ac7e
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ClfsLsnRecordSequence
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
req.alt-api: ClfsLsnRecordSequence
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
req.irql: Any level
req.iface: 
req.product: Windows 10 or later.
---

# ClfsLsnRecordSequence function



## -description
<p>The <b>ClfsLsnRecordSequence</b> routine returns the record sequence number contained in a specified LSN.</p>


## -syntax

````
ULONG ClfsLsnRecordSequence(
  _In_ const CLFS_LSN *plsn
);
````


## -parameters
<dl>

### -param <i>plsn</i> [in]

<dd>
<p>A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure from which the record sequence number is retrieved.</p>
</dd>
</dl>

## -returns
<p><b>ClfsLsnRecordSequence</b> returns the record sequence number contained in the LSN that is supplied by the caller.</p>

## -remarks
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-clfslsnblockoffset.md">ClfsLsnBlockOffset</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfslsncontainer.md">ClfsLsnContainer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnRecordSequence routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
