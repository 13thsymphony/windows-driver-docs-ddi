---
UID: NC:dispmprt.DXGKDDI_REMOVE_DEVICE
title: DXGKDDI_REMOVE_DEVICE
author: windows-driver-content
description: The DxgkDdiRemoveDevice function frees any resources allocated during DxgkDdiAddDevice.
old-location: display\dxgkddiremovedevice.htm
old-project: display
ms.assetid: 0d5f96e8-dcb3-49e5-8347-ba20d757618b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_REMOVE_DEVICE, DmFunctions_b8ab26af-93dd-4e49-b2a2-9c620678457d.xml, DxgkDdiRemoveDevice, DxgkDdiRemoveDevice callback function [Display Devices], display.dxgkddiremovedevice, dispmprt/DxgkDdiRemoveDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
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
-	DxgkDdiRemoveDevice
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKDDI_REMOVE_DEVICE callback function
The <i>DxgkDdiRemoveDevice</i> function frees any resources allocated during <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>.

## Syntax

```
DXGKDDI_REMOVE_DEVICE DxgkddiRemoveDevice;

NTSTATUS DxgkddiRemoveDevice(
  IN_CONST_PVOID MiniportDeviceContext
)
{...}
```

## Parameters

`MiniportDeviceContext`

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## Return Value

<i>DxgkDdiRemoveDevice </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

<i>DxgkDdiRemoveDevice</i> must free the context block represented by <i>MiniportDeviceContext</i>.

<i>DxgkDdiRemoveDevice</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>