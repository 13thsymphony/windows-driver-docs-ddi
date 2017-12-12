---
UID: NS.WDFUSB._WDF_USB_DEVICE_CREATE_CONFIG
title: _WDF_USB_DEVICE_CREATE_CONFIG
author: windows-driver-content
description: The WDF_USB_DEVICE_CREATE_CONFIG structure contains information that the framework uses to configure a framework USB device object.
old-location: wdf\wdf_usb_device_create_config.htm
old-project: wdf
ms.assetid: 717DFAE8-5F10-4443-AACA-07009060C23D
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_USB_DEVICE_CREATE_CONFIG, WDF_USB_DEVICE_CREATE_CONFIG, *PWDF_USB_DEVICE_CREATE_CONFIG
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
req.alt-api: WDF_USB_DEVICE_CREATE_CONFIG
req.alt-loc: wdfusb.h
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
req.product: Windows 10 or later.
---

# _WDF_USB_DEVICE_CREATE_CONFIG structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure contains information that the framework uses to configure a framework USB device object.



## -syntax

````
typedef struct _WDF_USB_DEVICE_CREATE_CONFIG {
  ULONG Size;
  ULONG USBDClientContractVersion;
} WDF_USB_DEVICE_CREATE_CONFIG, *PWDF_USB_DEVICE_CREATE_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field USBDClientContractVersion

The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602. 


## -remarks
The <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure is used as input to the <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a> method. To initialize a <b>WDF_USB_DEVICE_CREATE_CONFIG</b> structure, the driver must call <a href="wdf.wdf_usb_device_create_config_init">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows Vista

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
<dt>
<a href="wdf.wdf_usb_device_create_config_init">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_CREATE_CONFIG structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

