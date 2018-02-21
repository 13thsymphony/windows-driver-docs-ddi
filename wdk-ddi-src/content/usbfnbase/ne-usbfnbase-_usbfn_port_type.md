---
UID: NE:usbfnbase._USBFN_PORT_TYPE
title: "_USBFN_PORT_TYPE"
author: windows-driver-content
description: Defines the possible port types that can be returned by the client driver during port detection.
old-location: buses\usbfn_port_type.htm
old-project: usbref
ms.assetid: D45F8CD0-CB54-4DE4-BD6B-FF6A35FCBFEC
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UsbfnPortTypeMaximum, usbfnbase/UsbfnPortTypeMaximum, USBFN_PORT_TYPE, buses.usbfn_port_type, UsbfnStandardDownstreamPort, usbfnbase/UsbfnChargingDownstreamPort, usbfnbase/UsbfnDedicatedChargingPort, UsbfnInvalidDedicatedChargingPort, usbfnbase/UsbfnStandardDownstreamPort, UsbfnChargingDownstreamPort, usbfnbase/UsbfnInvalidDedicatedChargingPort, USBFN_PORT_TYPE enumeration [Buses], UsbfnUnknownPort, usbfnbase/UsbfnUnknownPort, *PUSBFN_PORT_TYPE, UsbfnDedicatedChargingPort, UsbfnProprietaryDedicatedChargingPort, usbfnbase/UsbfnProprietaryDedicatedChargingPort, usbfnbase/USBFN_PORT_TYPE, _USBFN_PORT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnbase.h
apiname:
-	USBFN_PORT_TYPE
product: Windows
targetos: Windows
req.typenames: "*PUSBFN_PORT_TYPE, USBFN_PORT_TYPE"
req.product: Windows 10 or later.
---

# _USBFN_PORT_TYPE Enumeration
Defines the possible port types that can be returned by the client driver during port detection.

## Syntax
````
typedef enum _USBFN_PORT_TYPE { 
  UsbfnUnknownPort                       = 0,
  UsbfnStandardDownstreamPort,
  UsbfnChargingDownstreamPort,
  UsbfnDedicatedChargingPort,
  UsbfnInvalidDedicatedChargingPort,
  UsbfnProprietaryDedicatedChargingPort,
  UsbfnPortTypeMaximum
} USBFN_PORT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UsbfnChargingDownstreamPort</td>
                    <td>The upstream port has been detected as a charging downstream port (CDP), as defined in the Battery Charging Specification, revision 1.2.</td>
                </tr>
            
                <tr>
                    <td>UsbfnDedicatedChargingPort</td>
                    <td>The upstream port has been detected as a dedicated charging port (DCP) (as defined in the Battery Charging Specification, revision 1.2).</td>
                </tr>
            
                <tr>
                    <td>UsbfnInvalidDedicatedChargingPort</td>
                    <td>The upstream port has been detected as a dedicated charging port that does not comply with the Battery Charging Specification, revision 1.2.</td>
                </tr>
            
                <tr>
                    <td>UsbfnPortTypeMaximum</td>
                    <td>The maximum value of the enumeration.</td>
                </tr>
            
                <tr>
                    <td>UsbfnProprietaryDedicatedChargingPort</td>
                    <td>A proprietary charger was attached.</td>
                </tr>
            
                <tr>
                    <td>UsbfnStandardDownstreamPort</td>
                    <td>The upstream port has been detected as a standard downstream port (SDP) (as defined in the Battery Charging Specification, revision 1.2).</td>
                </tr>
            
                <tr>
                    <td>UsbfnUnknownPort</td>
                    <td>Port detection was unable to determine the port type.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |

## See Also

<a href="..\usbfnattach\nc-usbfnattach-usbfn_get_attach_action.md">USBFN_GET_ATTACH_ACTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_PORT_TYPE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>