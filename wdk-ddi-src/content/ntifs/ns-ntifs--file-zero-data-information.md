---
UID: NS.ntifs._FILE_ZERO_DATA_INFORMATION
title: FILE_ZERO_DATA_INFORMATION
author: windows-driver-content
description: Contains a range of a file to set to zeros.
old-location: ifsk\file_zero_data_information.htm
old-project: ifsk
ms.assetid: 64F1A14F-2152-4095-A594-B2AE3B87C638
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FILE_ZERO_DATA_INFORMATION, FILE_ZERO_DATA_INFORMATION, *PFILE_ZERO_DATA_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_ZERO_DATA_INFORMATION
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

# FILE_ZERO_DATA_INFORMATION structure



## -description
<p>Contains a range of a file to set to zeros. This structure is used by the 
<a href="https://msdn.microsoft.com/library/windows/hardware/mt668765">FSCTL_SET_ZERO_DATA</a> control code. </p>


## -syntax

````
typedef struct _FILE_ZERO_DATA_INFORMATION {
  LARGE_INTEGER FileOffset;
  LARGE_INTEGER BeyondFinalZero;
} FILE_ZERO_DATA_INFORMATION, *PFILE_ZERO_DATA_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>FileOffset</b>

<dd>
<p>The file offset of the start of the range to set to zeros, in bytes.</p>
</dd>

### -field <b>BeyondFinalZero</b>

<dd>
<p>The byte offset of the first byte beyond the last zeroed byte.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows XP</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2003</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt668765">FSCTL_SET_ZERO_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt668764">FILE_ZERO_DATA_INFORMATION_EX</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_ZERO_DATA_INFORMATION structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
