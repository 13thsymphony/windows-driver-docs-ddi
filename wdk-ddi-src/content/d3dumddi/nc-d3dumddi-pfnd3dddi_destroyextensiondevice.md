---
UID: NC:d3dumddi.PFND3DDDI_DESTROYEXTENSIONDEVICE
title: PFND3DDDI_DESTROYEXTENSIONDEVICE
author: windows-driver-content
description: The DestroyExtensionDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.
old-location: display\destroyextensiondevice.htm
old-project: display
ms.assetid: 8c4bcab3-b903-4f39-aab0-7efb3b18d068
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DestroyExtensionDevice, DestroyExtensionDevice callback function [Display Devices], PFND3DDDI_DESTROYEXTENSIONDEVICE, UserModeDisplayDriver_Functions_6d9ce1e0-efda-4633-83fb-fa6a5aa5f37b.xml, d3dumddi/DestroyExtensionDevice, display.destroyextensiondevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DestroyExtensionDevice
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DESTROYEXTENSIONDEVICE callback function
The <b>DestroyExtensionDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.

## Syntax

```
PFND3DDDI_DESTROYEXTENSIONDEVICE Pfnd3dddiDestroyextensiondevice;

HRESULT Pfnd3dddiDestroyextensiondevice(
  HANDLE hDevice,
  HANDLE hExtension
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hExtension`

A handle to the DirectX VA extension device that the <a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a> function created.


## Return Value

<b>DestroyExtensionDevice</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA extension device.

## Remarks

The <b>DestroyExtensionDevice</b> function notifies the driver to destroy the handle to the DirectX VA extension device that the <a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA extension device handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>