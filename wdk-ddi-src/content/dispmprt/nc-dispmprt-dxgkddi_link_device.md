---
UID: NC:dispmprt.DXGKDDI_LINK_DEVICE
title: DXGKDDI_LINK_DEVICE
author: windows-driver-content
description: The optional DxgkDdiLinkDevice function queries the display miniport driver for information on the linked adapter configuration.
old-location: display\dxgkddilinkdevice.htm
old-project: display
ms.assetid: fb9b7c58-1c4f-42e4-a59f-4a529d3caca2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_LINK_DEVICE, DmFunctions_3dcba945-b441-49a2-9d1e-af0ff235136c.xml, DxgkDdiLinkDevice, DxgkDdiLinkDevice callback function [Display Devices], display.dxgkddilinkdevice, dispmprt/DxgkDdiLinkDevice
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
-	DxgkDdiLinkDevice
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKDDI_LINK_DEVICE callback function
The optional <i>DxgkDdiLinkDevice</i> function queries the display miniport driver for information on the linked adapter configuration.

## Syntax

```
DXGKDDI_LINK_DEVICE DxgkddiLinkDevice;

NTSTATUS DxgkddiLinkDevice(
  IN_CONST_PDEVICE_OBJECT PhysicalDeviceObject,
  IN_CONST_PVOID MiniportDeviceContext,
  INOUT_PLINKED_DEVICE LinkedDevice
)
{...}
```

## Parameters

`PhysicalDeviceObject`

A pointer to a physical device object (PDO) that identifies a display adapter.

`MiniportDeviceContext`

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.

`LinkedDevice`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568197">LINKED_DEVICE</a> structure that contains information on the linked display adapter configuration.


## Return Value

<i>DxgkDdiLinkDevice</i> returns STATUS_SUCCESS, or an appropriate error code if information on the linked adapter configuration cannot be obtained.

## Remarks

The <i>DxgkDdiLinkDevice</i> function should be implemented by drivers of display adapters that support linked display adapters.

If this function is provided, the operating system will query the display miniport driver for the linked adapter configuration immediately after a call is made to <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>.

If the operating system does not enumerate all the expected display adapters in the structure pointed to by <i>LinkedDevice</i>, the system will start in VGA mode.

The driver can enumerate only one leading link in the chain of linked display adapters.

Plug and Play or power events cause the leading linked adapter to power up or start after the remaining linked adapters, or, conversely, such events cause the leading linked adapter to power down or to be disabled before the remaining linked adapters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568197">LINKED_DEVICE</a>