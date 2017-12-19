---
UID: NS.USBBUSIF._USB_BUS_INTERFACE_USBDI_V3
title: _USB_BUS_INTERFACE_USBDI_V3
author: windows-driver-content
description: The USB_BUS_INTERFACE_USBDI_V3 structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs.
old-location: buses\usb_bus_interface_usbdi_v3.htm
old-project: UsbRef
ms.assetid: 1183f584-8dfa-4eea-b494-3a2e23ec0294
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3, PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_BUS_INTERFACE_USBDI_V3
req.alt-loc: usbbusif.h
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

# _USB_BUS_INTERFACE_USBDI_V3 structure



## -description
The <b>USB_BUS_INTERFACE_USBDI_V3</b> structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs. 



## -syntax

````
typedef struct _USB_BUS_INTERFACE_USBDI_V3 {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              BusContext;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  PUSB_BUSIFFN_GETUSBDI_VERSION      GetUSBDIVersion;
  PUSB_BUSIFFN_QUERY_BUS_TIME        QueryBusTime;
  PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB    SubmitIsoOutUrb;
  PUSB_BUSIFFN_QUERY_BUS_INFORMATION QueryBusInformation;
  PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED  IsDeviceHighSpeed;
  PUSB_BUSIFFN_ENUM_LOG_ENTRY        EnumLogEntry;
  PUSB_BUSIFFN_QUERY_BUS_TIME_EX     QueryBusTimeEx;
  PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE QueryControllerType;
} USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3;
````


## -struct-fields

### -field Size

Specifies the size in bytes of the buffer that holds the interface pointers. 


### -field Version

Indicates, on input, the version of the interface. The values that this member can take are as follows.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_0

</td>
<td>
Version 0 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_1

</td>
<td>
Version 1 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_2

</td>
<td>
Version 2 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_3

</td>
<td>
Version 3 of the interface.

</td>
</tr>
</table>
 


### -field BusContext

Contains information that describes the USB bus and the USB bus driver that exposes this interface. This is an opaque entity that the caller must pass to the interface routines. 


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="kernel.interfacereference">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="kernel.interfacedereference">InterfaceDereference</a>. 


### -field GetUSBDIVersion

Pointer to a routine that returns the USB interface version number, the version number of USB specification that defines the interface, along with host controller capabilities information. This routine returns the highest USBDI interface version supported by the port driver. For more information about this routine, see <a href="buses.getusbdiversion">GetUSBDIVersion</a>. 


### -field QueryBusTime

Pointer to a routine that returns the current 32-bit USB frame number. This routine replaces the <a href="buses.usbd_querybustime">USBD_QueryBusTime</a> function provided by usbd.sys. For more information about this routine, see <a href="buses.querybustime">QueryBusTime</a>.


### -field SubmitIsoOutUrb

Reserved. Do not use.


### -field QueryBusInformation

Pointer to a routine that retrieves information about the bus. The information that is returned depends on the value of the <b>Level </b>member. If <b>Level</b> is 0, this routine returns bus bandwidth information. If <b>Level</b> is 1, it returns bus bandwidth information and the host controller's symbolic name. This routine replaces the <b>USBD_QueryBusInformation</b> function provided by usbd.sys. For more information about this routine, see <a href="buses.querybusinformation">QueryBusInformation</a>. 


### -field IsDeviceHighSpeed

Pointer to a routine that determines if the USB device is operating at high speed. This routine returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device. Returns <b>FALSE</b> otherwise. For more information about this routine, see <a href="buses.isdevicehighspeed">IsDeviceHighSpeed</a>. 


### -field EnumLogEntry

Reserved. Do not use.


### -field QueryBusTimeEx

This routine is not implemented. 


### -field QueryControllerType

Pointer to a routine that returns information about the USB host controller the USB device is attached to. For more information about this routine, see <a href="buses.querycontrollertype">QueryControllerType</a>.


## -remarks
The <b>IsDeviceHighSpeed</b> routine does not indicate whether a device is capable of high-speed operation, but whether it is in fact operating at high speed. 

The routines in this structure must be callable at IRQL &gt;= DISPATCH_LEVEL. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows Vista and later operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbbusif.h (include Usbbusif.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_interfaces">Bus Driver Interface Routines for USB Client Drivers</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_BUS_INTERFACE_USBDI_V3 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

