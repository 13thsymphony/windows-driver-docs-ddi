---
UID: NS.WDFUSB._WDF_USB_INTERFACE_SETTING_PAIR
title: _WDF_USB_INTERFACE_SETTING_PAIR
author: windows-driver-content
description: The WDF_USB_INTERFACE_SETTING_PAIR structure specifies an alternate setting for a specified USB interface.
old-location: wdf\wdf_usb_interface_setting_pair.htm
old-project: wdf
ms.assetid: b6f169ae-6c4c-4c27-8532-75a76b66cc5a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_USB_INTERFACE_SETTING_PAIR, *PWDF_USB_INTERFACE_SETTING_PAIR, WDF_USB_INTERFACE_SETTING_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_INTERFACE_SETTING_PAIR
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

# _WDF_USB_INTERFACE_SETTING_PAIR structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_USB_INTERFACE_SETTING_PAIR</b> structure specifies an alternate setting for a specified USB interface.


## -syntax

````
typedef struct _WDF_USB_INTERFACE_SETTING_PAIR {
  WDFUSBINTERFACE UsbInterface;
  UCHAR           SettingIndex;
} WDF_USB_INTERFACE_SETTING_PAIR, *PWDF_USB_INTERFACE_SETTING_PAIR;
````


## -struct-fields

### -field UsbInterface

A handle to a framework USB interface object.

### -field SettingIndex

A device-specific index value that identifies an alternate setting for the interface. Alternate settings are described in the USB specification.

## -remarks
The <b>WDF_USB_INTERFACE_SETTING_PAIR</b> structure is used in the <a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.

## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
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
<a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_INTERFACE_SETTING_PAIR structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
