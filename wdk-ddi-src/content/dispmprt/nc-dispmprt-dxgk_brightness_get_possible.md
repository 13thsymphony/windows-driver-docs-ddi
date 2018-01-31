---
UID : NC:dispmprt.DXGK_BRIGHTNESS_GET_POSSIBLE
title : DXGK_BRIGHTNESS_GET_POSSIBLE
author : windows-driver-content
description : The DxgkDdiGetPossibleBrightness function retrieves the brightness levels that an integrated display panel supports.
old-location : display\dxgkddigetpossiblebrightness.htm
old-project : display
ms.assetid : aed565f5-a9c1-4130-a192-68bb699b4bd1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgkddigetpossiblebrightness, DxgkDdiGetPossibleBrightness callback function [Display Devices], DxgkDdiGetPossibleBrightness, DXGK_BRIGHTNESS_GET_POSSIBLE, DXGK_BRIGHTNESS_GET_POSSIBLE, dispmprt/DxgkDdiGetPossibleBrightness, DmFunctions_b14a6b62-e156-4548-9a0d-0a256cf84069.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
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
req.typenames : "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---


# DXGK_BRIGHTNESS_GET_POSSIBLE callback function
The <i>DxgkDdiGetPossibleBrightness</i> function retrieves the brightness levels that an integrated display panel supports.

## Syntax

```
DXGK_BRIGHTNESS_GET_POSSIBLE DxgkBrightnessGetPossible;

NTSTATUS DxgkBrightnessGetPossible(
  PVOID Context,
  ULONG BufferSize,
  PUCHAR LevelCount,
  PUCHAR BrightnessLevels
)
{...}
```

## Parameters

`Context`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.

`BufferSize`

[in] The size, in bytes, of the buffer that is passed in the <i>BrightnessLevels</i> parameter.

`LevelCount`

[out] A pointer to a variable that receives the number of brightness levels that the driver returns in the buffer that the <i>BrightnessLevels</i> parameter points to.

`BrightnessLevels`

[in/out] A pointer to a buffer that receives the brightness levels that an integrated display panel supports.


## Return Value

<i>DxgkDdiGetPossibleBrightness</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>.

## Remarks

The display miniport driver should return brightness levels in the buffer that the <i>BrightnessLevels</i> parameter points to in the following order:
<ul>
<li>
The first brightness level value is the brightness level that the BIOS uses when the computer runs on AC power. 

</li>
<li>
The second brightness level value is the brightness level that the BIOS uses when the computer runs on DC power. 

</li>
<li>
The remaining brightness level values are hardware-supported brightness levels. 

</li>
</ul>To simplify your job of implementing a display miniport driver, the operating system provides the driver with the buffer that the <i>BrightnessLevels</i> parameter points to.

<i>DxgkDdiGetPossibleBrightness</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_GET_POSSIBLE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>