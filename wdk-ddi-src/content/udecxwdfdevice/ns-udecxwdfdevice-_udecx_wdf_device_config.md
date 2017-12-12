---
UID: NS.UDECXWDFDEVICE._UDECX_WDF_DEVICE_CONFIG
title: _UDECX_WDF_DEVICE_CONFIG
author: windows-driver-content
description: Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling UDECX_WDF_DEVICE_CONFIG_INIT.
old-location: buses\udecx_wdf_device_config.htm
old-project: usbref
ms.assetid: 54853C39-FA6C-4F9B-A202-F116C43D3A4E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG, UDECX_WDF_DEVICE_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UDECX_WDF_DEVICE_CONFIG
req.alt-loc: udecxwdfdevice.h
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
req.product: Windows 10 or later.
---

# _UDECX_WDF_DEVICE_CONFIG structure



## -description
Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling <a href="buses.udecx_wdf_device_config_init">UDECX_WDF_DEVICE_CONFIG_INIT</a>.



## -syntax

````
typedef struct _UDECX_WDF_DEVICE_CONFIG {
  ULONG                                     Size;
  USHORT                                    NumberOfUsb20Ports;
  USHORT                                    NumberOfUsb30Ports;
  PFN_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY EvtUdecxWdfDeviceQueryUsbCapability;
  UDECX_WDF_DEVICE_RESET_ACTION             ResetAction;
  PFN_UDECX_WDF_DEVICE_RESET                EvtUdecxWdfDeviceReset;
} UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG;
````


## -struct-fields

### -field Size

The size of this structure.


### -field NumberOfUsb20Ports

The number of USB 2.0 ports on the root hub of the emulated host controller.


### -field NumberOfUsb30Ports

The number of USB 3.0 ports on the root hub of the emulated host controller.


### -field EvtUdecxWdfDeviceQueryUsbCapability

A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability.md">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.


### -field ResetAction

A <a href="buses.udecx_wdf_device_reset_action">UDECX_WDF_DEVICE_RESET_ACTION</a>-type value that indicates the reset action: each attached device or the host controller.


### -field EvtUdecxWdfDeviceReset

A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a> callback function.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Udecxwdfdevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.udecx_wdf_device_config_init">UDECX_WDF_DEVICE_CONFIG_INIT</a>
</dt>
<dt>
<a href="buses.udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_WDF_DEVICE_CONFIG structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

