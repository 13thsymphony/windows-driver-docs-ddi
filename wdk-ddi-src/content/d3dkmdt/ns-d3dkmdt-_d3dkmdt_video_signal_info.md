---
UID: NS.D3DKMDT._D3DKMDT_VIDEO_SIGNAL_INFO
title: _D3DKMDT_VIDEO_SIGNAL_INFO
author: windows-driver-content
description: The D3DKMDT_VIDEO_SIGNAL_INFO structure contains information about a video signal driven by a video output on a display adapter.
old-location: display\d3dkmdt_video_signal_info.htm
old-project: display
ms.assetid: 38d0a655-265b-46e0-8af3-de6757025588
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMDT_VIDEO_SIGNAL_INFO, D3DKMDT_VIDEO_SIGNAL_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDEO_SIGNAL_INFO
req.alt-loc: d3dkmdt.h
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

# _D3DKMDT_VIDEO_SIGNAL_INFO structure



## -description
The D3DKMDT_VIDEO_SIGNAL_INFO structure contains information about a video signal driven by a video output on a display adapter.



## -syntax

````
typedef struct _D3DKMDT_VIDEO_SIGNAL_INFO {
  D3DKMDT_VIDEO_SIGNAL_STANDARD VideoStandard;
  D3DKMDT_2DREGION              TotalSize;
  D3DKMDT_2DREGION              ActiveSize;
  D3DDDI_RATIONAL               VSyncFreq;
  D3DDDI_RATIONAL               HSyncFreq;
  SIZE_T                        PixelRate;
  union {
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
    struct {
      D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING ScanLineOrdering  :3;
      UINT                                  VSyncFreqDivider  :6;
      UINT                                  Reserved  :23;
    } AdditionalSignalInfo;
#endif 
    D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING ScanLineOrdering;
  };
} D3DKMDT_VIDEO_SIGNAL_INFO;
````


## -struct-fields

### -field VideoStandard

A constant from the <a href="display.d3dkmdt_video_signal_standard">D3DKMDT_VIDEO_SIGNAL_STANDARD</a> enumeration that indicates the video standard (if any) that defines the video signal.


### -field TotalSize

A <a href="display.d3dkmdt_2dregion">D3DKMDT_2DREGION</a> structure that specifies the width and height (in pixels) of the entire video signal.


### -field ActiveSize

A D3DKMDT_2DREGION structure that specifies the width and height (in pixels) of the active portion of the video signal.


### -field VSyncFreq

A <a href="display.d3dddi_rational">D3DDDI_RATIONAL</a> structure that specifies the vertical refresh rate in Hz.


### -field HSyncFreq

A D3DDDI_RATIONAL structure that specifies the horizontal refresh rate in Hz.


### -field PixelRate

The pixel clock rate.


### -field AdditionalSignalInfo

Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.


### -field ScanLineOrdering

A constant from the <a href="display.d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a> enumeration that indicates the scanline ordering (for example, progressive or interlaced) of the video signal.

Supported starting with Windows 8.1.


### -field VSyncFreqDivider

The ratio of the VSync rate of a monitor that displays through a Miracast connected session to the VSync rate of the Miracast sink.

To avoid visual artifacts, the VSync rate of the display monitor that's connected to the Miracast sink must be an integer multiple of the VSync rate of the Miracast sink. The display miniport driver reports the latter rate to the operating system as the refresh rate of the desktop present path.

<div class="alert"><b>Note</b>  The operating system fails any attempt by the driver to add a target mode that results in a Miracast target having a VSync rate below 23.9 Hz.</div>
<div> </div>
For a non-Miracast target, the driver should set <b>VSyncFreqDivider</b> to zero.

Supported starting with Windows 8.1.


### -field Reserved

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.

</dd>
</dl>

### -field ScanLineOrdering

A constant from the <a href="display.d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a> enumeration that indicates the scanline ordering (for example, progressive or interlaced) of the video signal.


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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>
</dt>
<dt>
<a href="display.d3dkmdt_video_present_target">D3DKMDT_VIDEO_PRESENT_TARGET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_SIGNAL_INFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

