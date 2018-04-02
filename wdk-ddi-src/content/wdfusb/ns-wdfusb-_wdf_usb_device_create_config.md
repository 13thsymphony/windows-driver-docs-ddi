---
UID: NS:wdfusb._WDF_USB_DEVICE_CREATE_CONFIG
title: "_WDF_USB_DEVICE_CREATE_CONFIG"
author: windows-driver-content
description: The WDF_USB_DEVICE_CREATE_CONFIG structure contains information that the framework uses to configure a framework USB device object.
old-location: wdf\wdf_usb_device_create_config.htm
old-project: wdf
ms.assetid: 717DFAE8-5F10-4443-AACA-07009060C23D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_USB_DEVICE_CREATE_CONFIG, PWDF_USB_DEVICE_CREATE_CONFIG, PWDF_USB_DEVICE_CREATE_CONFIG structure pointer, WDF_USB_DEVICE_CREATE_CONFIG, WDF_USB_DEVICE_CREATE_CONFIG structure, _WDF_USB_DEVICE_CREATE_CONFIG, kmdf.wdf_usb_device_create_config, kmdf.wdf_usbtarget_device_config, wdf.wdf_usb_device_create_config, wdfusb/PWDF_USB_DEVICE_CREATE_CONFIG, wdfusb/WDF_USB_DEVICE_CREATE_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
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
-	WDF_USB_DEVICE_CREATE_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_USB_DEVICE_CREATE_CONFIG, *PWDF_USB_DEVICE_CREATE_CONFIG
req.product: Windows 10 or later.
---

# _WDF_USB_DEVICE_CREATE_CONFIG structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure contains information that the framework uses to configure a framework USB device object.

## Syntax
```
typedef struct _WDF_USB_DEVICE_CREATE_CONFIG {
  ULONG Size;
  ULONG USBDClientContractVersion;
} *PWDF_USB_DEVICE_CREATE_CONFIG, WDF_USB_DEVICE_CREATE_CONFIG;
```

## Members


`Size`

The size, in bytes, of this structure.

`USBDClientContractVersion`

The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602.

## Remarks
The <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a> method. To initialize a <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406507">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista Windows Vista |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406507">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>