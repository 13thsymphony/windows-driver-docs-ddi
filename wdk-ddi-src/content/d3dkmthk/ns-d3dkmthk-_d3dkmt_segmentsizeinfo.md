---
UID: NS:d3dkmthk._D3DKMT_SEGMENTSIZEINFO
title: _D3DKMT_SEGMENTSIZEINFO
author: windows-driver-content
description: The D3DKMT_SEGMENTSIZEINFO structure describes the size, in bytes, of memory and aperture segments.
old-location: display\d3dkmt_segmentsizeinfo.htm
old-project: display
ms.assetid: 16c7b4bd-efc9-4cce-8677-8046038d1c76
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SEGMENTSIZEINFO, D3DKMT_SEGMENTSIZEINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SEGMENTSIZEINFO
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_SEGMENTSIZEINFO
---

# _D3DKMT_SEGMENTSIZEINFO structure



## -description
The D3DKMT_SEGMENTSIZEINFO structure describes the size, in bytes, of memory and aperture segments.



## -syntax

````
typedef struct _D3DKMT_SEGMENTSIZEINFO {
  ULONGLONG DedicatedVideoMemorySize;
  ULONGLONG DedicatedSystemMemorySize;
  ULONGLONG SharedSystemMemorySize;
} D3DKMT_SEGMENTSIZEINFO;
````


## -struct-fields

### -field DedicatedVideoMemorySize

[out] The size, in bytes, of memory that is dedicated from video memory.


### -field DedicatedSystemMemorySize

[out] The size, in bytes, of memory that is dedicated from system memory.


### -field SharedSystemMemorySize

[out] The size, in bytes, of memory from system memory that can be shared by many users.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SEGMENTSIZEINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

