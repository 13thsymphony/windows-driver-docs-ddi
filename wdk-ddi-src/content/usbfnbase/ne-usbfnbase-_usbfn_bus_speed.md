---
UID: NE:usbfnbase._USBFN_BUS_SPEED
title: "_USBFN_BUS_SPEED"
author: windows-driver-content
description: The USBFN_BUS_SPEED enumeration defines possible bus speeds.
old-location: buses\usbfn_bus_speed.htm
old-project: UsbRef
ms.assetid: B97E27A1-0D95-41AA-8FF6-A92F70FBAD28
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: usbfnbase/UsbfnBusSpeedSuper, UsbfnBusSpeedHigh, *PUSBFN_BUS_SPEED, usbfnbase/USBFN_BUS_SPEED, USBFN_BUS_SPEED, usbfnbase/UsbfnBusSpeedLow, usbfnbase/UsbfnBusSpeedMaximum, UsbfnBusSpeedLow, usbfnbase/UsbfnBusSpeedHigh, _USBFN_BUS_SPEED, UsbfnBusSpeedFull, usbfnbase/UsbfnBusSpeedFull, UsbfnBusSpeedSuper, UsbfnBusSpeedMaximum, buses.usbfn_bus_speed, USBFN_BUS_SPEED enumeration [Buses]
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
-	USBFN_BUS_SPEED
product: Windows
targetos: Windows
req.typenames: "*PUSBFN_BUS_SPEED, USBFN_BUS_SPEED"
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
                    <td>UsbfnBusSpeedFull</td>
                    <td>A full bandwidth bus speed of 12 MBit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedHigh</td>
                    <td>A high bus speed of 480 Mbit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedLow</td>
                    <td>A low bandwidth bus speed of 1.5 Mbit per second.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedMaximum</td>
                    <td>The maximum value of the enumeration.</td>
                </tr>
            
                <tr>
                    <td>UsbfnBusSpeedSuper</td>
                    <td>A SuperSpeed mode bus speed of 5 Gbit per second.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |