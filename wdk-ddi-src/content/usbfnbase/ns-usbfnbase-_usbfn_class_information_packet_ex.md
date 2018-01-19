---
UID : NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET_EX
title : _USBFN_CLASS_INFORMATION_PACKET_EX
author : windows-driver-content
description : Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.
old-location : buses\usbfn_class_information_packet_ex.htm
old-project : usbref
ms.assetid : 373D7CA9-AF1B-46E8-AE6A-F693A9214527
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBFN_CLASS_INFORMATION_PACKET_EX, *PUSBFN_CLASS_INFORMATION_PACKET_EX, USBFN_CLASS_INFORMATION_PACKET_EX
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbfnbase.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBFN_CLASS_INFORMATION_PACKET_EX
req.alt-loc : usbfnbase.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PUSBFN_CLASS_INFORMATION_PACKET_EX, USBFN_CLASS_INFORMATION_PACKET_EX"
req.product : Windows 10 or later.
---

# _USBFN_CLASS_INFORMATION_PACKET_EX structure
Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.

## Syntax
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

## Members

        
            `HasInterfaceGuid`

            Determines whether the driver has published a device interface is GUID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbfnbase.h |

    ## See Also

        <dl>
<dt>
<a href="..\usbfnbase\ns-usbfnbase-_usbfn_class_interface.md">USBFN_CLASS_INTERFACE</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatesymboliclink.md">WdfDeviceCreateSymbolicLink</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md">WdfDeviceSetDeviceInterfaceState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_CLASS_INFORMATION_PACKET_EX structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>