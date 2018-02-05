---
UID : NC:dispmprt.DXGK_BRIGHTNESS_GET_CAPS
title : DXGK_BRIGHTNESS_GET_CAPS
author : windows-driver-content
description : Retrieves brightness control capabilities of an integrated display panel.
old-location : display\dxgkddigetbrightnesscaps.htm
old-project : display
ms.assetid : 3418dd2b-63cb-411f-9bae-390148885907
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgkddigetbrightnesscaps, DxgkDdiGetBrightnessCaps callback function [Display Devices], DxgkDdiGetBrightnessCaps, DXGK_BRIGHTNESS_GET_CAPS, DXGK_BRIGHTNESS_GET_CAPS, dispmprt/DxgkDdiGetBrightnessCaps
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGK_BRIGHTNESS_GET_CAPS callback function
Retrieves brightness control capabilities of an integrated display panel.

## Syntax

```
DXGK_BRIGHTNESS_GET_CAPS DxgkBrightnessGetCaps;

NTSTATUS DxgkBrightnessGetCaps(
  PVOID Context,
  DXGK_BRIGHTNESS_CAPS *BrightnessCaps
)
{...}
```

## Parameters

`Context`

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

`*BrightnessCaps`

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md">DXGK_BRIGHTNESS_CAPS</a> structure that represents the brightness control capabilities of the display panel.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

## Remarks

This function lets the display miniport driver independently indicate its support for adaptive brightness control and/or smooth brightness control.

If the hardware includes an ambient light sensor, it must support smooth brightness control. The display miniport driver, not an embedded controller, must control the smooth brightness functioning of the integrated display panel.

If the driver is started by a Plug and Play (PnP) event, it must  transition smoothly from the initial brightness level set by firmware to the level set by the operating system. If additional devices are connected to the system, they must not affect the driver's ability to perform smooth brightness  control on the integrated display panel.

The driver must continue to support smooth brightness control even if adaptive brightness control is initiated.

This function should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md">DXGK_BRIGHTNESS_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_GET_CAPS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>