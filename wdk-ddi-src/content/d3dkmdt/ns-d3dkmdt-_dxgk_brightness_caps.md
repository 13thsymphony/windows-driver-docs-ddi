---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_CAPS
title: "_DXGK_BRIGHTNESS_CAPS"
author: windows-driver-content
description: Identifies brightness control capabilities of an integrated display panel that the display miniport driver provides through a call to its DxgkDdiGetBrightnessCaps function.
old-location: display\dxgk_brightness_caps.htm
old-project: display
ms.assetid: e01ef4c9-1374-4d60-9307-32d878759c72
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_BRIGHTNESS_CAPS, DXGK_BRIGHTNESS_CAPS structure [Display Devices], _DXGK_BRIGHTNESS_CAPS, d3dkmdt/DXGK_BRIGHTNESS_CAPS, display.dxgk_brightness_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	D3dkmdt.h
api_name:
-	DXGK_BRIGHTNESS_CAPS
product: Windows
targetos: Windows
req.typenames: DXGK_BRIGHTNESS_CAPS
---

# _DXGK_BRIGHTNESS_CAPS structure
Identifies brightness control capabilities of an integrated display panel that the display miniport driver provides through a call to its <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps.md">DxgkDdiGetBrightnessCaps</a> function. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.

## Syntax
````
typedef struct _DXGK_BRIGHTNESS_CAPS {
  union {
    struct {
      UINT SmoothBrightness  :1;
      UINT AdaptiveBrightness  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} DXGK_BRIGHTNESS_CAPS;
````

## Members


## Remarks
Do not assume that the <b>SmoothBrightness</b> members of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a> and <b>DXGK_BRIGHTNESS_CAPS</b> are the same. <b>DXGK_BRIGHTNESS_STATE</b>.<b>SmoothBrightness</b> is used to enable  smooth brightness control on an integrated display panel. <b>DXGK_BRIGHTNESS_CAPS</b>.<b>SmoothBrightness</b> is used to query smooth brightness control capabilities of the integrated display panel.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a>



<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps.md">DxgkDdiGetBrightnessCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_CAPS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>