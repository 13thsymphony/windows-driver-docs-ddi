---
UID: NF.udecxwdfdevice.UDECX_WDF_DEVICE_CONFIG_INIT
title: UDECX_WDF_DEVICE_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UDECX_WDF_DEVICE_CONFIG structure.
old-location: buses\udecx_wdf_device_config_init.htm
old-project: UsbRef
ms.assetid: EC26EDCA-1C9E-4D06-A970-71FB96FEB0DF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UDECX_WDF_DEVICE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UDECX_WDF_DEVICE_CONFIG_INIT
req.alt-loc: Udecxstub.lib,Udecxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UDECX_WDF_DEVICE_CONFIG_INIT function



## -description
Initializes a <a href="buses.udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> structure.



## -syntax

````
FORCEINLINE void UDECX_WDF_DEVICE_CONFIG_INIT(
  _Out_ PUDECX_WDF_DEVICE_CONFIG                  Config,
  _In_  PFN_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY EvtUdecxWdfDeviceQueryUsbCapability
);
````


## -parameters

### -param Config [out]

A pointer to a <a href="buses.udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> structure to initialize.


### -param EvtUdecxWdfDeviceQueryUsbCapability [in]

A pointer to an <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability.md">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Udecxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a>
</dt>
<dt>
<a href="buses.udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UDECX_WDF_DEVICE_CONFIG_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

