---
UID: NS:d3dkmthk._D3DKMT_WORKINGSETINFO
title: _D3DKMT_WORKINGSETINFO
author: windows-driver-content
description: The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_workingsetinfo.htm
old-project: display
ms.assetid: 1a5b75e4-abdd-4916-b2b5-4dbb53a525ae
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_WORKINGSETINFO, D3DKMT_WORKINGSETINFO
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
req.alt-api: D3DKMT_WORKINGSETINFO
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
req.typenames: D3DKMT_WORKINGSETINFO
---

# _D3DKMT_WORKINGSETINFO structure



## -description
The D3DKMT_WORKINGSETINFO structure describes information about the graphics adapter's working set that the OpenGL installable client driver (ICD) obtains by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> function.



## -syntax

````
typedef struct _D3DKMT_WORKINGSETINFO {
  D3DKMT_WORKINGSETFLAGS Flags;
  ULONG                  MinimumWorkingSetPercentile;
  ULONG                  MaximumWorkingSetPercentile;
} D3DKMT_WORKINGSETINFO;
````


## -struct-fields

### -field Flags

[out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetflags.md">D3DKMT_WORKINGSETFLAGS</a> structure that indicates, in bit-field flags, working-set properties.


### -field MinimumWorkingSetPercentile

[out] The minimum working-set percentile. 


### -field MaximumWorkingSetPercentile

[out] The maximum working-set percentile. 


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
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetflags.md">D3DKMT_WORKINGSETFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WORKINGSETINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

