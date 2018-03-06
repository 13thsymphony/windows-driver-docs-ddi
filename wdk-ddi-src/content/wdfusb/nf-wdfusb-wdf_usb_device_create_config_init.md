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
req.lib: NtosKrnl.exe
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
  initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_create_config.md">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

## Syntax

````
void WDF_USB_DEVICE_CREATE_CONFIG_INIT(
  _Out_ PWDF_USB_DEVICE_CREATE_CONFIG Config,
  _In_  ULONG                         USBDClientContractVersion
);
````

## Parameters

`Config`

A pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_create_config.md">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

`USBDClientContractVersion`

The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602.


## Return Value

This function does not return a value.

## Remarks

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function zeros the specified <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_create_config.md">WDF_USB_DEVICE_CREATE_CONFIG</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the structure's <b>USBDClientContractVersion</b> member to the specified value.

For a code example that uses <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b>, see <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows Vista  |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_create_config.md">WDF_USB_DEVICE_CREATE_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_CREATE_CONFIG_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>