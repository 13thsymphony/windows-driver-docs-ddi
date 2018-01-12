---
UID: NS:d3dkmthk._D3DKMT_CREATEOVERLAY
title: _D3DKMT_CREATEOVERLAY
author: windows-driver-content
description: The D3DKMT_CREATEOVERLAY structure describes overlay hardware.
old-location: display\d3dkmt_createoverlay.htm
old-project: display
ms.assetid: b020b06c-72e2-4322-a5db-fcfc46db429e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CREATEOVERLAY, D3DKMT_CREATEOVERLAY
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
req.alt-api: D3DKMT_CREATEOVERLAY
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
req.typenames: D3DKMT_CREATEOVERLAY
---

# _D3DKMT_CREATEOVERLAY structure



## -description
The D3DKMT_CREATEOVERLAY structure describes overlay hardware.



## -syntax

````
typedef struct _D3DKMT_CREATEOVERLAY {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_KERNELOVERLAYINFO       OverlayInfo;
  D3DKMT_HANDLE                  hOverlay;
} D3DKMT_CREATEOVERLAY;
````


## -struct-fields

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which to overlay (that is, the identifier of the primary surface on which to overlay). 


### -field hDevice

[in] A handle to the device that the overlay is associated with.


### -field OverlayInfo

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a> structure that describes information about the kernel-mode overlay object.


### -field hOverlay

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode overlay object, which represents the overlay hardware in subsequent calls by the OpenGl ICD.


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
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateoverlay.md">D3DKMTCreateOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

