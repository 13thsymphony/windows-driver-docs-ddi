---
UID: NC.dispmprt.DXGK_BRIGHTNESS_SET_STATE
title: DXGK_BRIGHTNESS_SET_STATE
author: windows-driver-content
description: Enables smooth brightness control on an integrated display panel.
old-location: display\dxgkddisetbrightnessstate.htm
old-project: display
ms.assetid: 804046ff-0cc7-4ff0-be07-b574cb40fd2b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, PSYMBOL_INFO_EX, *PSYMBOL_INFO_EX
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
req.alt-api: DxgkDdiSetBrightnessState
req.alt-loc: Dispmprt.h
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
---

# DXGK_BRIGHTNESS_SET_STATE callback



## -description
Enables smooth brightness control on an integrated display panel.



## -prototype

````
DXGK_BRIGHTNESS_SET_STATE DxgkDdiSetBrightnessState;

NTSTATUS* DxgkDdiSetBrightnessState(
  _In_ PVOID                 Context,
  _In_ DXGK_BRIGHTNESS_STATE *BrightnessState
)
{ ... }
````


## -parameters

### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param BrightnessState [in]

A pointer to a <a href="display.dxgk_brightness_state">DXGK_BRIGHTNESS_STATE</a> structure that indicates that the display miniport driver should enable the smooth brightness control for the integrated display panel.


## -returns
Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.


## -remarks
For the operating system to be able to adjust screen brightness smoothly, starting with Windows 8 the display miniport driver must report 10 brightness levels, expressed from 0 to 100 percent. At a level of zero percent, the screen contents should be barely visible to the user. A level of 100 percent is the maximum brightness that the integrated display panel can produce. The driver and hardware can support finer brightness control for internal operations.

When the <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function is called, the driver should select an appropriate slope to provide a smooth brightness transition based on panel characteristics, but any transition must complete in under 500 milliseconds.

This function should be made pageable.


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
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_SET_STATE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

