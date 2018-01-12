---
UID: NS:d3dkmthk._D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
title: _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
author: windows-driver-content
description: The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmt_checkvidpnexclusiveownership.htm
old-project: display
ms.assetid: 5a7f05a0-11ae-49ed-9015-f2712cc77880
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
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
req.typenames: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
---

# _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure



## -description
The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.



## -syntax

````
typedef struct _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP;
````


## -struct-fields

### -field hAdapter

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the graphics adapter. 


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to check about. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system. 

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
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcheckvidpnexclusiveownership.md">D3DKMTCheckVidPnExclusiveOwnership</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

