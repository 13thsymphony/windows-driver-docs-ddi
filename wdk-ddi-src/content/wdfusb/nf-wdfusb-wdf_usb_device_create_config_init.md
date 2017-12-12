---
UID: NF.wdfusb.WDF_USB_DEVICE_CREATE_CONFIG_INIT
title: WDF_USB_DEVICE_CREATE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_USB_DEVICE_CREATE_CONFIG_INIT function initializes a WDF_USB_DEVICE_CREATE_CONFIG structure.
old-location: wdf\wdf_usb_device_create_config_init.htm
old-project: wdf
ms.assetid: 01053A65-45A4-4232-A9F2-1651DC820026
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_USB_DEVICE_CREATE_CONFIG_INIT
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
req.alt-api: WDF_USB_DEVICE_CREATE_CONFIG_INIT
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

# WDF_USB_DEVICE_CREATE_CONFIG_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function
  initializes a <a href="wdf.wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure. 



## -syntax

````
void WDF_USB_DEVICE_CREATE_CONFIG_INIT(
  _Out_ PWDF_USB_DEVICE_CREATE_CONFIG Config,
  _In_  ULONG                         USBDClientContractVersion
);
````


## -parameters

### -param Config [out]

A pointer to a <a href="wdf.wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.


### -param USBDClientContractVersion [in]

The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602. 


## -returns
This function does not return a value.


## -remarks
The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function zeros the specified <a href="wdf.wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the structure's <b>USBDClientContractVersion</b> member to the specified value.

For a code example that uses <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b>, see <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<a href="wdf.wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_CREATE_CONFIG_INIT function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

