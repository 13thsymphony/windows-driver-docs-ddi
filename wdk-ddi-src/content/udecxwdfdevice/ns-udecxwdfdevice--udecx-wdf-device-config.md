---
UID: NS.udecxwdfdevice._UDECX_WDF_DEVICE_CONFIG
title: UDECX_WDF_DEVICE_CONFIG
author: windows-driver-content
description: Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling UDECX_WDF_DEVICE_CONFIG_INIT.
old-location: buses\udecx_wdf_device_config.htm
old-project: usbref
ms.assetid: 54853C39-FA6C-4F9B-A202-F116C43D3A4E
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UDECX_WDF_DEVICE_CONFIG, UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG
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
req.iface: 
req.product: Windows 10 or later.
---

# UDECX_WDF_DEVICE_CONFIG structure



## -description
<p>Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecx-wdf-device-config-init.md">UDECX_WDF_DEVICE_CONFIG_INIT</a>.</p>


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
<dl>

### -field Size

<dd>
<p>The size of this structure.</p>
</dd>

### -field NumberOfUsb20Ports

<dd>
<p>The number of USB 2.0 ports on the root hub of the emulated host controller.</p>
</dd>

### -field NumberOfUsb30Ports

<dd>
<p>The number of USB 3.0 ports on the root hub of the emulated host controller.</p>
</dd>

### -field EvtUdecxWdfDeviceQueryUsbCapability

<dd>
<p>A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt-udecx-wdf-device-query-usb-capability.md">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.</p>
</dd>

### -field ResetAction

<dd>
<p>A <a href="..\udecxwdfdevice\ne-udecxwdfdevice--udecx-wdf-device-reset-action.md">UDECX_WDF_DEVICE_RESET_ACTION</a>-type value that indicates the reset action: each attached device or the host controller.</p>
</dd>

### -field EvtUdecxWdfDeviceReset

<dd>
<p>A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt-udecx-wdf-device-reset.md">EVT_UDECX_WDF_DEVICE_RESET</a> callback function.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecx-wdf-device-config-init.md">UDECX_WDF_DEVICE_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_WDF_DEVICE_CONFIG structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
