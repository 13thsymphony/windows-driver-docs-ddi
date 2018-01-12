---
UID: NS:d3dkmddi._DXGKARG_ISSUPPORTEDVIDPN
title: _DXGKARG_ISSUPPORTEDVIDPN
author: windows-driver-content
description: The DXGKARG_ISSUPPORTEDVIDPN structure contains arguments for the DxgkDdiIsSupportedVidPn function. The DxgkDdiIsSupportedVidPn function determines whether a specified video present network (VidPN) is supported on a display adapter.
old-location: display\dxgkarg_issupportedvidpn.htm
old-project: display
ms.assetid: 37f9f40d-6d32-4eeb-8161-282a84ee89dc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_ISSUPPORTEDVIDPN, DXGKARG_ISSUPPORTEDVIDPN, *INOUT_PDXGKARG_ISSUPPORTEDVIDPN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_ISSUPPORTEDVIDPN
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGKARG_ISSUPPORTEDVIDPN
---

# _DXGKARG_ISSUPPORTEDVIDPN structure



## -description
The DXGKARG_ISSUPPORTEDVIDPN structure contains arguments for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a> function. The <i>DxgkDdiIsSupportedVidPn</i> function determines whether a specified video present network (VidPN) is supported on a display adapter.



## -syntax

````
typedef struct _DXGKARG_ISSUPPORTEDVIDPN {
  D3DKMDT_HVIDPN hDesiredVidPn;
  BOOLEAN        IsVidPnSupported;
} DXGKARG_ISSUPPORTEDVIDPN;
````


## -struct-fields

### -field hDesiredVidPn

A handle to the VidPN object in question.


### -field IsVidPnSupported

A Boolean variable that receives <b>TRUE</b> if the VidPN is supported and <b>FALSE</b> if the VidPN is not supported.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_ISSUPPORTEDVIDPN structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

