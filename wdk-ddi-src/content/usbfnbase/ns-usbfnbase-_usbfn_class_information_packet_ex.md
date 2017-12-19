---
UID: NS.USBFNBASE._USBFN_CLASS_INFORMATION_PACKET_EX
title: _USBFN_CLASS_INFORMATION_PACKET_EX
author: windows-driver-content
description: Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.
old-location: buses\usbfn_class_information_packet_ex.htm
old-project: UsbRef
ms.assetid: 373D7CA9-AF1B-46E8-AE6A-F693A9214527
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USBFN_CLASS_INFORMATION_PACKET_EX, USBFN_CLASS_INFORMATION_PACKET_EX, PUSBFN_CLASS_INFORMATION_PACKET_EX, *PUSBFN_CLASS_INFORMATION_PACKET_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBFN_CLASS_INFORMATION_PACKET_EX
req.alt-loc: usbfnbase.h
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

# _USBFN_CLASS_INFORMATION_PACKET_EX structure



## -description
Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions. 



## -syntax

````
typedef struct _USBFN_CLASS_INFORMATION_PACKET_EX {
  USBFN_CLASS_INTERFACE_EX FullSpeedClassInterface;
  USBFN_CLASS_INTERFACE_EX HighSpeedClassInterface;
  USBFN_CLASS_INTERFACE    SuperSpeedClassInterface;
  WCHAR                    InterfaceName[MAX_INTERFACE_NAME_LENGTH];
  WCHAR                    InterfaceGuid[MAX_INTERFACE_GUID_LENGTH];
  BOOLEAN                  HasInterfaceGuid;
} USBFN_CLASS_INFORMATION_PACKET_EX, *PUSBFN_CLASS_INFORMATION_PACKET_EX;
````


## -struct-fields

### -field FullSpeedClassInterface

A <a href="buses.usbfn_class_interface_ex">USBFN_CLASS_INTERFACE_EX</a> structure that describes an interface for full speed device.


### -field HighSpeedClassInterface

A <a href="buses.usbfn_class_interface_ex">USBFN_CLASS_INTERFACE_EX</a> structure that describes an interface for high speed device.


### -field SuperSpeedClassInterface

A <a href="buses.usbfn_class_interface">USBFN_CLASS_INTERFACE</a> structure that describes an interface for SuperSpeed device.


### -field InterfaceName[MAX_INTERFACE_NAME_LENGTH]

A string that contains the interface name.


### -field InterfaceGuid[MAX_INTERFACE_GUID_LENGTH]

A string from which the driver can derive the device interface GUID.


### -field HasInterfaceGuid

Determines whether the driver has published a device interface is GUID. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnbase.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usbfn_class_interface">USBFN_CLASS_INTERFACE</a>
</dt>
<dt>
<a href="wdf.wdfdevicecreatesymboliclink">WdfDeviceCreateSymbolicLink</a>
</dt>
<dt>
<a href="wdf.wdfdevicesetdeviceinterfacestate">WdfDeviceSetDeviceInterfaceState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBFN_CLASS_INFORMATION_PACKET_EX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

