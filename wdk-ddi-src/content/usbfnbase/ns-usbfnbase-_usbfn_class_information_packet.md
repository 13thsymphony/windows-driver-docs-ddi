---
UID: NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET
title: "_USBFN_CLASS_INFORMATION_PACKET"
author: windows-driver-content
description: Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.
old-location: buses\usbfn_class_information_packet.htm
old-project: usbref
ms.assetid: 18A07670-B610-4D09-8BF0-3C55E781A68B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET structure pointer [Buses], USBFN_CLASS_INFORMATION_PACKET, USBFN_CLASS_INFORMATION_PACKET structure [Buses], _USBFN_CLASS_INFORMATION_PACKET, buses.usbfn_class_information_packet, usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET, usbfnbase/USBFN_CLASS_INFORMATION_PACKET"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_CLASS_INFORMATION_PACKET
product: Windows
targetos: Windows
req.typenames: USBFN_CLASS_INFORMATION_PACKET, *PUSBFN_CLASS_INFORMATION_PACKET
req.product: Windows 10 or later.
---

# _USBFN_CLASS_INFORMATION_PACKET structure
Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.

## Syntax
````
typedef struct _USBFN_CLASS_INFORMATION_PACKET {
  USBFN_CLASS_INTERFACE FullSpeedClassInterface;
  USBFN_CLASS_INTERFACE HighSpeedClassInterface;
  WCHAR                 InterfaceName[MAX_INTERFACE_NAME_LENGTH];
  WCHAR                 InterfaceGuid[MAX_INTERFACE_GUID_LENGTH];
  BOOLEAN               HasInterfaceGuid;
  USBFN_CLASS_INTERFACE SuperSpeedClassInterface;
} USBFN_CLASS_INFORMATION_PACKET, *PUSBFN_CLASS_INFORMATION_PACKET;
````

## Members


`FullSpeedClassInterface`

A <a href="..\usbfnbase\ns-usbfnbase-_usbfn_class_interface.md">USBFN_CLASS_INTERFACE</a> structure that describes an interface for full speed device.

`HasInterfaceGuid`

Determines whether the driver has published a device interface is GUID.

`HighSpeedClassInterface`

A <a href="..\usbfnbase\ns-usbfnbase-_usbfn_class_interface.md">USBFN_CLASS_INTERFACE</a> structure that describes an interface for high speed device.

`InterfaceGuid`



`InterfaceName`



`SuperSpeedClassInterface`

A <a href="..\usbfnbase\ns-usbfnbase-_usbfn_class_interface.md">USBFN_CLASS_INTERFACE</a> structure that describes an interface for SuperSpeed device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md">WdfDeviceSetDeviceInterfaceState</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatesymboliclink.md">WdfDeviceCreateSymbolicLink</a>



<a href="..\usbfnbase\ns-usbfnbase-_usbfn_class_interface.md">USBFN_CLASS_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_CLASS_INFORMATION_PACKET structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>