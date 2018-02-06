---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_STATE
title: DXGK_BRIGHTNESS_SET_STATE
author: windows-driver-content
description: Enables smooth brightness control on an integrated display panel.
old-location: display\dxgkddisetbrightnessstate.htm
old-project: display
ms.assetid: 804046ff-0cc7-4ff0-be07-b574cb40fd2b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddisetbrightnessstate, DxgkDdiSetBrightnessState callback function [Display Devices], DxgkDdiSetBrightnessState, DXGK_BRIGHTNESS_SET_STATE, DXGK_BRIGHTNESS_SET_STATE, dispmprt/DxgkDdiSetBrightnessState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkDdiSetBrightnessState
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---


# DXGK_BRIGHTNESS_SET_STATE callback function
Enables smooth brightness control on an integrated display panel.

## Syntax

```
DXGK_BRIGHTNESS_SET_STATE DxgkBrightnessSetState;

NTSTATUS DxgkBrightnessSetState(
  PVOID Context,
  DXGK_BRIGHTNESS_STATE *BrightnessState
)
{...}
```

## Parameters

`Context`

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

`*BrightnessState`

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_state.md">DXGK_BRIGHTNESS_STATE</a> structure that indicates that the display miniport driver should enable the smooth brightness control for the integrated display panel.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

## Remarks

For the operating system to be able to adjust screen brightness smoothly, starting with Windows 8 the display miniport driver must report 10 brightness levels, expressed from 0 to 100 percent. At a level of zero percent, the screen contents should be barely visible to the user. A level of 100 percent is the maximum brightness that the integrated display panel can produce. The driver and hardware can support finer brightness control for internal operations.

When the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function is called, the driver should select an appropriate slope to provide a smooth brightness transition based on panel characteristics, but any transition must complete in under 500 milliseconds.

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

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_SET_STATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>