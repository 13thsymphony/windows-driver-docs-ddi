---
UID: NF.ntifs.RtlIsPartialPlaceholder
title: RtlIsPartialPlaceholder
author: windows-driver-content
description: The RtlIsPartialPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file.
old-location: ifsk\rtlispartialplaceholder.htm
old-project: ifsk
ms.assetid: FB47F5BE-76B4-4A99-A15F-DE3E11D1DA2B
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlIsPartialPlaceholder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlIsPartialPlaceholder
req.alt-loc: Ntifs.h
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

# RtlIsPartialPlaceholder function



## -description
<p>The <b>RtlIsPartialPlaceholder</b> routine determines if a file or a directory is a CloudFiles placeholder,
    based on the <b>FileAttributes</b> and <b>ReparseTag</b> values of the file. These values can be obtained by listing the directory containing the file or by directly querying <b>FileAttributeTagInfo</b> on the file.</p>


## -syntax

````
BOOLEAN RtlIsPartialPlaceholder(
  _In_ ULONG FileAttributes,
  _In_ ULONG ReparseTag
);
````


## -parameters
<dl>

### -param FileAttributes [in]

<dd>
<p>Specifies the file attributes of a file or directory.</p>
</dd>

### -param ReparseTag [in]

<dd>
<p>The ReparseTag or EaSize of a file or directory.</p>
</dd>
</dl>

## -returns
<p>This function returns <b>TRUE</b> if the file or directory is a partial placeholder. It  returns <b>FALSE</b> if either the
        file or directory is not a placeholder or is a full placeholder.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 10, version 1709.</p>
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
<a href="..\ntifs\nf-ntifs-rtlispartialplaceholderfileinfo.md">RtlIsPartialPlaceholderFileInfo</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlispartialplaceholderfilehandle.md">RtlIsPartialPlaceholderFileHandle</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsPartialPlaceholder routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
