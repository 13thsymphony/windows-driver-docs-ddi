---
UID: NE.usbfnbase._USBFN_PORT_TYPE
title: _USBFN_PORT_TYPE
author: windows-driver-content
description: Defines the possible port types that can be returned by the client driver during port detection.
old-location: buses\usbfn_port_type.htm
old-project: UsbRef
ms.assetid: D45F8CD0-CB54-4DE4-BD6B-FF6A35FCBFEC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USBFN_PORT_TYPE, *PUSBFN_PORT_TYPE, USBFN_PORT_TYPE, PUSBFN_PORT_TYPE
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
req.alt-api: USBFN_PORT_TYPE
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

# _USBFN_PORT_TYPE enumeration



## -description
Defines the possible port types that can be returned by the client driver during port detection.



## -syntax

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


## -enum-fields

### -field UsbfnUnknownPort

Port detection was unable to determine the port type.


### -field UsbfnStandardDownstreamPort

The upstream port has been detected as a standard downstream port (SDP) (as defined in the Battery Charging Specification, revision 1.2).


### -field UsbfnChargingDownstreamPort

The upstream port has been detected as a charging downstream port (CDP), as defined in the Battery Charging Specification, revision 1.2.


### -field UsbfnDedicatedChargingPort

The upstream port has been detected as a dedicated charging port (DCP) (as defined in the Battery Charging Specification, revision 1.2).


### -field UsbfnInvalidDedicatedChargingPort

The upstream port has been detected as a dedicated charging port that does not comply with the Battery Charging Specification, revision 1.2.


### -field UsbfnProprietaryDedicatedChargingPort

A proprietary charger was attached.


### -field UsbfnPortTypeMaximum

The maximum value of the enumeration.


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
<a href="..\usbfnattach\nc-usbfnattach-usbfn_get_attach_action.md">USBFN_GET_ATTACH_ACTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBFN_PORT_TYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

