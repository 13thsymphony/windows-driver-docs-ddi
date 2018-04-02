---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET
title: DXGK_BRIGHTNESS_SET
author: windows-driver-content
description: The DxgkDdiSetBrightness function sets a new brightness level.
old-location: display\dxgkddisetbrightness.htm
old-project: display
ms.assetid: 83609679-20df-463d-ac3a-bb8a87897608
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_BRIGHTNESS_SET, DmFunctions_7b5ff27a-7a8f-4dee-8b3d-c9b0df76db6d.xml, DxgkDdiSetBrightness, DxgkDdiSetBrightness callback function [Display Devices], display.dxgkddisetbrightness, dispmprt/DxgkDdiSetBrightness
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiSetBrightness
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGK_BRIGHTNESS_SET callback function
The <i>DxgkDdiSetBrightness</i> function sets a new brightness level.

## Syntax

```
DXGK_BRIGHTNESS_SET DxgkBrightnessSet;

NTSTATUS DxgkBrightnessSet(
  PVOID Context,
  UCHAR Brightness
)
{...}
```

## Parameters

`Context`

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.

`Brightness`

The brightness level value to set.


## Return Value

<i>DxgkDdiSetBrightness</i> returns STATUS_SUCCESS if it succeeds in setting a new brightness level. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

The <a href="https://msdn.microsoft.com/6352c3fd-1a5f-4137-b76e-35c5b82a56c7">monitor driver</a> calls the display miniport driver's <i>DxgkDdiSetBrightness</i> function to change the brightness level of the integrated display panel for the following reasons:

<ul>
<li>
Notifications from the Device Power Policy Engine (DPPE) indicate that either the current policy is modified or a new policy takes effect. A new DPPE policy takes effect on system start, resume, and user switch, as well as when the power source is changed.

</li>
<li>
The preferred way for user-mode clients to control brightness is through Windows Management Instrumentation (WMI). The monitor driver implements the WMI brightness controls that select a brightness level or revert the brightness level to the level that was selected by the currently active DPPE policy. The WMI method to select a brightness level overrides the current DPPE policy level until any change in DPPE policy occurs. When DPPE policy changes, the new DPPE level is set. 

</li>
<li>
For compatibility with the <a href="https://msdn.microsoft.com/24cb232b-e289-45c8-8d55-42614a4dfd54">Windows 2000 Display Driver Model</a>, the monitor driver implements <a href="https://msdn.microsoft.com/library/windows/hardware/ff568140">IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS</a> as an alternative way for user-mode clients to control brightness. A call to IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS is handled the same way as the WMI brightness control that selects a brightness level. 

</li>
<li>
The monitor driver interprets brightness hot-key notifications from the Advanced Configuration and Power Interface (ACPI) driver as user requests to change the current brightness level. As with the WMI and IOCTL user-mode interfaces, a change in brightness level that is triggered by a hot-key notification overrides the current DPPE policy and stays in effect until DPPE policy requests that the brightness value is set again.

</li>
</ul>
<i>DxgkDdiSetBrightness</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568140">IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS</a>