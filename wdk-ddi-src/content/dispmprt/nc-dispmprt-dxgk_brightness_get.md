---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET
title: DXGK_BRIGHTNESS_GET
author: windows-driver-content
description: The DxgkDdiGetBrightness function retrieves the currently active brightness level of an integrated display panel.
old-location: display\dxgkddigetbrightness.htm
old-project: display
ms.assetid: e226cd36-45af-4d80-9aba-8919b267483b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
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
req.alt-api: DxgkDdiGetBrightness
req.alt-loc: dispmprt.h
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
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGK_BRIGHTNESS_GET callback



## -description
The <i>DxgkDdiGetBrightness</i> function retrieves the currently active brightness level of an integrated display panel.



## -prototype

````
DXGK_BRIGHTNESS_GET DxgkDdiGetBrightness;

NTSTATUS* DxgkDdiGetBrightness(
  _In_ PVOID  Context,
  _In_ PUCHAR Brightness
)
{ ... }
````


## -parameters

### -param Context [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param Brightness [in]

A pointer to a variable that receives the brightness level. 


## -returns
<i>DxgkDdiGetBrightness</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 


## -remarks
When the <a href="https://msdn.microsoft.com/6352c3fd-1a5f-4137-b76e-35c5b82a56c7">monitor driver</a> initializes, it can call the display miniport driver's <i>DxgkDdiGetBrightness</i> function to retrieve the brightness level that will be currently active for the integrated display panel.

Because the monitor driver always gets the brightness level for the integrated display panel on boot or resume and all changes in brightness go through the monitor driver, the monitor driver should always have the current brightness level cached. Therefore, when clients query for the current brightness level, the level is queried from the monitor driver and not from the display miniport driver.

<i>DxgkDdiGetBrightness</i> should be made pageable.


## -requirements
<table>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_GET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

