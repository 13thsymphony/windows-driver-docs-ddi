---
UID: NS:d3dkmthk._D3DKMT_BRIGHTNESS_INFO
title: "_D3DKMT_BRIGHTNESS_INFO"
author: windows-driver-content
description: Contains information about the brightness of an integrated display panel.
old-location: display\d3dkmt_brightness_info.htm
old-project: display
ms.assetid: a620b0b2-85ce-4373-a50c-299d8ce7a91c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_BRIGHTNESS_INFO, D3DKMT_BRIGHTNESS_INFO structure [Display Devices], _D3DKMT_BRIGHTNESS_INFO, d3dkmthk/D3DKMT_BRIGHTNESS_INFO, display.d3dkmt_brightness_info
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_BRIGHTNESS_INFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_BRIGHTNESS_INFO
---

# _D3DKMT_BRIGHTNESS_INFO structure
Contains information about the brightness of an integrated display panel.

## Syntax
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

## Members


`Type`

A value of type <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_brightness_info_type.md">D3DKMT_BRIGHTNESS_INFO_TYPE</a> that  indicates the type of brightness information to retrieve or set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_backlight_info.md">DXGK_BACKLIGHT_INFO</a>



<a href="..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md">DXGK_BACKLIGHT_OPTIMIZATION_LEVEL</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_brightness_info_type.md">D3DKMT_BRIGHTNESS_INFO_TYPE</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md">DXGK_BRIGHTNESS_CAPS</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_brightness_possible_levels.md">D3DKMT_BRIGHTNESS_POSSIBLE_LEVELS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_BRIGHTNESS_INFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>