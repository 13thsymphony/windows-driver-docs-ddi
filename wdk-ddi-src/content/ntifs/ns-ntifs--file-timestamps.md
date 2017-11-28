---
UID: NS.ntifs._FILE_TIMESTAMPS
title: FILE_TIMESTAMPS
author: windows-driver-content
description: The FILE_TIMESTAMPS structure specifies the last recorded instance of specific actions on a file.
old-location: ifsk\file_timestamps.htm
old-project: ifsk
ms.assetid: 0F016D21-34CD-43DD-BE39-C6DF6D63A3AC
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FILE_TIMESTAMPS, FILE_TIMESTAMPS, *PFILE_TIMESTAMPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_TIMESTAMPS
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

# FILE_TIMESTAMPS structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>FILE_TIMESTAMPS</b> structure specifies the last recorded instance of specific actions on a file.</p>


## -syntax

````
typedef struct _File_TIMESTAMPS {
  LARGE_INTEGER CreationTime;
  LARGE_INTEGER LastAccessTime;
  LARGE_INTEGER LastWriteTime;
  LARGE_INTEGER ChangeTime;
} FILE_TIMESTAMPS, *PFILE_TIMESTAMPS;
````


## -struct-fields
<dl>

### -field <b>CreationTime</b>

<dd>
<p>Specifies the creation time of a file.</p>
</dd>

### -field <b>LastAccessTime</b>

<dd>
<p>Specifies the last time a file was accessed.</p>
</dd>

### -field <b>LastWriteTime</b>

<dd>
<p>Specifies the last time a file was written to.</p>
</dd>

### -field <b>ChangeTime</b>

<dd>
<p>Specifies the last time a file was changed or modified.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt734230">ATOMIC_CREATE_ECP_CONTEXT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_TIMESTAMPS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
