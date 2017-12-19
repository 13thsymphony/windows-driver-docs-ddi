---
UID: NS.D3DKMTHK._D3DKMT_SETDISPLAYMODE
title: _D3DKMT_SETDISPLAYMODE
author: windows-driver-content
description: The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display.
old-location: display\d3dkmt_setdisplaymode.htm
old-project: display
ms.assetid: cb590e18-59a4-4c4d-9d97-9f60c409c2e9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_SETDISPLAYMODE, D3DKMT_SETDISPLAYMODE
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
req.alt-api: D3DKMT_SETDISPLAYMODE
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
---

# _D3DKMT_SETDISPLAYMODE structure



## -description
The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display. 



## -syntax

````
typedef struct _D3DKMT_SETDISPLAYMODE {
  D3DKMT_HANDLE                         hDevice;
  D3DKMT_HANDLE                         hPrimaryAllocation;
  D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING ScanLineOrdering;
  D3DDDI_ROTATION                       DisplayOrientation;
  UINT                                  PrivateDriverFormatAttribute;
  D3DKMT_SETDISPLAYMODE_FLAGS           Flags;
} D3DKMT_SETDISPLAYMODE;
````


## -struct-fields

### -field hDevice

[in] A handle to the device that requests setting of the display mode.


### -field hPrimaryAllocation

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the primary allocation for scanning out. 


### -field ScanLineOrdering

[in] A <a href="display.d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field DisplayOrientation

[in] A <a href="display.d3dddi_rotation">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field PrivateDriverFormatAttribute

[out] A UINT value that specifies a private format attribute that the OpenGL installable client driver (ICD) should use to convert the current primary surface if a call to the <a href="display.d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a> function failed with STATUS_GRAPHICS_INCOMPATIBLE_PRIVATE_FORMAT. 


### -field Flags

Supported in Windows 7 and later versions.

[in] A <a href="display.d3dkmt_setdisplaymode_flags">D3DKMT_SETDISPLAYMODE_FLAGS</a> structure that specifies, in bit-field flags, attributes for setting the display mode. 


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
<a href="display.d3dddi_rotation">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="display.d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>
</dt>
<dt>
<a href="display.d3dkmt_setdisplaymode_flags">D3DKMT_SETDISPLAYMODE_FLAGS</a>
</dt>
<dt>
<a href="display.d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETDISPLAYMODE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

