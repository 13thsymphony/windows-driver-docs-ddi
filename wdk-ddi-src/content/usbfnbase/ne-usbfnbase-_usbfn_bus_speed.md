---
UID: NE:usbfnbase._USBFN_BUS_SPEED
title: "_USBFN_BUS_SPEED"
author: windows-driver-content
description: The USBFN_BUS_SPEED enumeration defines possible bus speeds.
old-location: buses\usbfn_bus_speed.htm
old-project: usbref
ms.assetid: B97E27A1-0D95-41AA-8FF6-A92F70FBAD28
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBFN_BUS_SPEED, USBFN_BUS_SPEED, USBFN_BUS_SPEED enumeration [Buses], UsbfnBusSpeedFull, UsbfnBusSpeedHigh, UsbfnBusSpeedLow, UsbfnBusSpeedMaximum, UsbfnBusSpeedSuper, _USBFN_BUS_SPEED, buses.usbfn_bus_speed, usbfnbase/USBFN_BUS_SPEED, usbfnbase/UsbfnBusSpeedFull, usbfnbase/UsbfnBusSpeedHigh, usbfnbase/UsbfnBusSpeedLow, usbfnbase/UsbfnBusSpeedMaximum, usbfnbase/UsbfnBusSpeedSuper"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_BUS_SPEED
product: Windows
targetos: Windows
req.typenames: USBFN_BUS_SPEED, *PUSBFN_BUS_SPEED
req.product: Windows 10 or later.
---

# _USBFN_BUS_SPEED Enumeration
The <b>USBFN_BUS_SPEED</b> enumeration defines possible bus speeds.

## Syntax
````
typedef enum _USBFN_BUS_SPEED { 
  UsbfnBusSpeedLow,
  UsbfnBusSpeedFull,
  UsbfnBusSpeedHigh,
  UsbfnBusSpeedSuper,
  UsbfnBusSpeedMaximum
} USBFN_BUS_SPEED;
````

## Constants

<table>
            
                <tr>
                    <td>UsbfnBusSpeedLow</td>
                    <td>A low bandwidth bus speed of 1.5 Mbit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedFull</td>
                    <td>A full bandwidth bus speed of 12 MBit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedHigh</td>
                    <td>A high bus speed of 480 Mbit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedSuper</td>
                    <td>A SuperSpeed mode bus speed of 5 Gbit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedMaximum</td>
                    <td>The maximum value of the enumeration.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |