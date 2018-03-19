---
UID: NS:dispmprt.DXGK_BRIGHTNESS_INTERFACE_2
title: DXGK_BRIGHTNESS_INTERFACE_2
author: windows-driver-content
description: Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.
old-location: display\dxgk_brightness_interface_2.htm
old-project: display
ms.assetid: 0c0b877f-cef0-4e98-9f37-60f2d96b81bd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2, DXGK_BRIGHTNESS_INTERFACE_2 structure [Display Devices], PDXGK_BRIGHTNESS_INTERFACE_2, PDXGK_BRIGHTNESS_INTERFACE_2 structure pointer [Display Devices], display.dxgk_brightness_interface_2, dispmprt/DXGK_BRIGHTNESS_INTERFACE_2, dispmprt/PDXGK_BRIGHTNESS_INTERFACE_2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_BRIGHTNESS_INTERFACE_2
product: Windows
targetos: Windows
req.typenames: DXGK_BRIGHTNESS_INTERFACE_2, *PDXGK_BRIGHTNESS_INTERFACE_2
---

# DXGK_BRIGHTNESS_INTERFACE_2 structure
Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control.

## Syntax
````
typedef struct {
  USHORT                                     Size;
  USHORT                                     Version;
  PVOID                                      Context;
  PINTERFACE_REFERENCE                       InterfaceReference;
  PINTERFACE_DEREFERENCE                     InterfaceDereference;
  DXGK_BRIGHTNESS_GET_POSSIBLE               GetPossibleBrightness;
  DXGK_BRIGHTNESS_SET                        SetBrightness;
  DXGK_BRIGHTNESS_GET                        GetBrightness;
  DXGK_BRIGHTNESS_GET_CAPS                   GetBrightnessCaps;
  DXGK_BRIGHTNESS_SET_STATE                  SetBrightnessState;
  DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION SetBacklightOptimization;
  DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION    GetBacklightReduction;
} DXGK_BRIGHTNESS_INTERFACE_2, *PDXGK_BRIGHTNESS_INTERFACE_2;
````

## Members


`Size`

[in] The size, in bytes, of this structure.

`Version`

[in] The version number of the brightness interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_BRIGHTNESS_INTERFACE_VERSION_2</b>).

`Context`

[in] A pointer to a private context block.

`InterfaceReference`

[out] A pointer to an interface reference function that is implemented by the display miniport driver.

`InterfaceDereference`

[out] A pointer to an interface dereference function that is implemented by the display miniport driver.

`GetPossibleBrightness`

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_possible.md">DxgkDdiGetPossibleBrightness</a> function.

`SetBrightness`

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function.

`GetBrightness`

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get.md">DxgkDdiGetBrightness</a> function.

`GetBrightnessCaps`

[out] A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_caps.md">DxgkDdiGetBrightnessCaps</a> function. This function is available starting with Windows 8.

`SetBrightnessState`

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_state.md">DxgkDdiSetBrightnessState</a> function. This function is available starting with Windows 8.

`SetBacklightOptimization`

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set_backlight_optimization.md">DxgkDdiSetBacklightOptimization</a> function. This function is available starting with Windows 8.

`GetBacklightReduction`

[out] A pointer to the display miniport driver's  <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_backlight_reduction.md">DxgkDdiGetBacklightReduction</a> function. This function is available starting with Windows 8.

## Remarks
This structure provides additional members, beyond those in the <a href="..\dispmprt\ns-dispmprt-dxgk_brightness_interface.md">DXGK_BRIGHTNESS_INTERFACE</a> interface, that point to driver-implemented functions that control, measure, and optimize display panel brightness and allow smooth brightness control.

For more information on this interface, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj647485">Brightness Control Interface V. 2 (Adaptive and Smooth Brightness Control)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="..\dispmprt\ns-dispmprt-dxgk_brightness_interface.md">DXGK_BRIGHTNESS_INTERFACE</a>