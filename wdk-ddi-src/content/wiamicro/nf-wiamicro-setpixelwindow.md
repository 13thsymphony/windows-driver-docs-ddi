---
UID: NF:wiamicro.SetPixelWindow
title: SetPixelWindow function
author: windows-driver-content
description: The SetPixelWindow function sets the image area to be scanned.
old-location: image\setpixelwindow.htm
old-project: image
ms.assetid: e1b5af5d-9bb8-4bf0-898a-5972f1f09a35
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SetPixelWindow function [Imaging Devices], SetPixelWindow, MicroDrv_45542a77-e61e-49ba-a9f3-df7d8dd57402.xml, wiamicro/SetPixelWindow, image.setpixelwindow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiamicro.h
apiname:
-	SetPixelWindow
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# SetPixelWindow function
The <b>SetPixelWindow </b>function sets the image area to be scanned.

## Syntax

````
WIAMICRO_API HRESULT SetPixelWindow(
  _Inout_ PSCANINFO pScanInfo,
          LONG      x,
          LONG      y,
          LONG      xExtent,
          LONG      yExtent
);
````

## Parameters

`pScanInfo`

Points to a <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure that represents the current state of the device. This is stored by the WIA Flatbed driver to guarantee synchronized settings between the microdriver and the WIA Flatbed driver.

`x`

Specifies the horizontal position value for the left side of the selection rectangle in pixels.

`y`

Specifies the vertical position value for the top of the selection rectangle in pixels.

`xExtent`

Specifies the width of the selection rectangle in pixels.

`yExtent`

Specifies the height of the selection rectangle in pixels.


## Return Value

If the function succeeds, it returns S_OK. If the function fails, it returns a standard COM error code.

## Remarks

In this function, the microdriver should set up the <b>Window</b> member of the <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure, making any device-specific adjustments that are necessary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | wiamicro.h (include Wiamicro.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552722">WIA Microdriver Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20SetPixelWindow function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>