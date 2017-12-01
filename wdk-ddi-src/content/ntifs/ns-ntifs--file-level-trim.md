---
UID: NS.ntifs._FILE_LEVEL_TRIM
title: FILE_LEVEL_TRIM
author: windows-driver-content
description: The FILE_LEVEL_TRIM structure contains an array of byte ranges to trim for a file.
old-location: ifsk\file_level_trim.htm
old-project: ifsk
ms.assetid: 72FD2A3B-B246-41BA-BEB6-169C214C32D7
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FILE_LEVEL_TRIM, FILE_LEVEL_TRIM, *PFILE_LEVEL_TRIM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_LEVEL_TRIM
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# FILE_LEVEL_TRIM structure



## -description
<p>The <b>FILE_LEVEL_TRIM</b> structure contains an array of byte ranges to trim for a file.</p>


## -syntax

````
typedef struct _FILE_LEVEL_TRIM {
  ULONG                 Key;
  ULONG                 NumRanges;
  FILE_LEVEL_TRIM_RANGE Ranges[1];
} FILE_LEVEL_TRIM, *PFILE_LEVEL_TRIM;
````


## -struct-fields
<dl>

### -field <b>Key</b>

<dd>
<p>The key for the byte range locks. Most callers will set this to 0. Remote file systems use <b>Key</b> for tagging a set of range locks.</p>
</dd>

### -field <b>NumRanges</b>

<dd>
<p>Total number of range structures in <b>Ranges</b>.</p>
</dd>

### -field <b>Ranges</b>

<dd>
<p>Array of trim ranges for a file.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 8 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs--file-level-trim-range.md">FILE_LEVEL_TRIM_RANGE</a>
</dt>
<dt>
<a href="ifsk.fsctl_file_level_trim">FSCTL_FILE_LEVEL_TRIM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LEVEL_TRIM structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
