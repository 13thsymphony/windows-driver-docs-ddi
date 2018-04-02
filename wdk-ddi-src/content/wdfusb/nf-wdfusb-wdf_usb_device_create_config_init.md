---
UID: NF:wdfusb.WDF_USB_DEVICE_CREATE_CONFIG_INIT
title: WDF_USB_DEVICE_CREATE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_USB_DEVICE_CREATE_CONFIG_INIT function initializes a WDF_USB_DEVICE_CREATE_CONFIG structure.
old-location: wdf\wdf_usb_device_create_config_init.htm
old-project: wdf
ms.assetid: 01053A65-45A4-4232-A9F2-1651DC820026
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_USB_DEVICE_CREATE_CONFIG_INIT, WDF_USB_DEVICE_CREATE_CONFIG_INIT function, kmdf.wdf_usb_device_create_config_init, kmdf.wdf_usbtarget_device_config_init, wdf.wdf_usb_device_create_config_init, wdfusb/WDF_USB_DEVICE_CREATE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
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
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_DEVICE_CREATE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WDF_USB_DEVICE_CREATE_CONFIG_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function
  initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406503">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

## Syntax

```
void WDF_USB_DEVICE_CREATE_CONFIG_INIT(
  PWDF_USB_DEVICE_CREATE_CONFIG Config,
  ULONG                         USBDClientContractVersion
);
```

## Parameters

`Config`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406503">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

`USBDClientContractVersion`

The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602.


## Return Value

This function does not return a value.

## Remarks

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/hh406503">WDF_USB_DEVICE_CREATE_CONFIG</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the structure's <b>USBDClientContractVersion</b> member to the specified value.

For a code example that uses <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista  |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406503">WDF_USB_DEVICE_CREATE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>