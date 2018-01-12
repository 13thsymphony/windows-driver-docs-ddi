---
UID: NS:d3dkmthk._D3DKMT_BRIGHTNESS_INFO
title: _D3DKMT_BRIGHTNESS_INFO
author: windows-driver-content
description: Contains information about the brightness of an integrated display panel.
old-location: display\d3dkmt_brightness_info.htm
old-project: display
ms.assetid: a620b0b2-85ce-4373-a50c-299d8ce7a91c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_BRIGHTNESS_INFO, D3DKMT_BRIGHTNESS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_BRIGHTNESS_INFO
req.alt-loc: D3dkmthk.h
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
req.typenames: D3DKMT_BRIGHTNESS_INFO
---

# _D3DKMT_BRIGHTNESS_INFO structure



## -description
Contains information about the brightness of an integrated display panel.



## -syntax

````
typedef struct _D3DKMT_BRIGHTNESS_INFO {
  D3DKMT_BRIGHTNESS_INFO_TYPE Type;
  union {
    D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS PossibleLevels;
    UCHAR                             Brightness;
    DXGK_BRIGHTNESS_CAPS              BrightnessCaps;
    DXGK_BRIGHTNESS_STATE             BrightnessState;
    DXGK_BACKLIGHT_OPTIMIZATION_LEVEL OptimizationLevel;
    DXGK_BACKLIGHT_INFO               ReductionInfo;
    BOOLEAN                           VerboseLogging;
  };
} D3DKMT_BRIGHTNESS_INFO;
````


## -struct-fields

### -field Type

A value of type <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_brightness_info_type.md">D3DKMT_BRIGHTNESS_INFO_TYPE</a> that  indicates the type of brightness information to retrieve or set.


### -field PossibleLevels

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_brightness_possible_levels.md">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a> structure that contains information about all possible brightness levels that the integrated display panel supports.


### -field Brightness

The current brightness level.


### -field BrightnessCaps

A <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md">DXGK_BRIGHTNESS_CAPS</a> structure that represents the brightness control capabilities of the integrated display panel.


### -field BrightnessState

A <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a> structure that represents the smooth brightness control capabilities of the integrated display panel.


### -field OptimizationLevel

A <a href="..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a> structure that represents the optimization level of brightness control.


### -field ReductionInfo

A value of type <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_backlight_info.md">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.


### -field VerboseLogging

A boolean value that indicates whether Event Tracing for Windows (ETW) logging of brightness information should be verbose.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_brightness_info_type.md">D3DKMT_BRIGHTNESS_INFO_TYPE</a>
</dt>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_brightness_possible_levels.md">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_backlight_info.md">DXGK_BACKLIGHT_INFO</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md">DXGK_BRIGHTNESS_CAPS</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_BRIGHTNESS_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

