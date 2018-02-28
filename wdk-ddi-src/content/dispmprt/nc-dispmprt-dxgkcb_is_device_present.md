---
UID: NC:dispmprt.DXGKCB_IS_DEVICE_PRESENT
title: DXGKCB_IS_DEVICE_PRESENT
author: windows-driver-content
description: The DxgkCbIsDevicePresent function determines whether a specified PCI device is present.
old-location: display\dxgkcbisdevicepresent.htm
old-project: display
ms.assetid: 82716a1a-e361-40ad-b3cd-bdcd3abc75f8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKCB_IS_DEVICE_PRESENT, DpFunctions_0ef5f8dd-52b6-4bf6-a19b-f87043ff6d18.xml, DxgkCbIsDevicePresent, DxgkCbIsDevicePresent callback function [Display Devices], display.dxgkcbisdevicepresent, dispmprt/DxgkCbIsDevicePresent
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
-	DxgkCbIsDevicePresent
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKCB_IS_DEVICE_PRESENT callback function
The <b>DxgkCbIsDevicePresent</b> function determines whether a specified PCI device is present.

## Syntax

```
DXGKCB_IS_DEVICE_PRESENT DxgkcbIsDevicePresent;

NTSTATUS DxgkcbIsDevicePresent(
  HANDLE DeviceHandle,
  PPCI_DEVICE_PRESENCE_PARAMETERS DevicePresenceParameters,
  PBOOLEAN DevicePresent
)
{...}
```

## Parameters

`DeviceHandle`

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.

`DevicePresenceParameters`

A pointer to a PCI_DEVICE_PRESENCE_PARAMETERS structure (defined in <i>Wdm.h</i>) that the caller fills in with information that identifies the device.

`DevicePresent`

A pointer to a Boolean variable that receives <b>TRUE</b> if the device is present or <b>FALSE</b> if the device is not present.


## Return Value

<b>DxgkCbIsDevicePresent</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL |