---
UID: NS:usb._USBD_ENDPOINT_OFFLOAD_INFORMATION
title: "_USBD_ENDPOINT_OFFLOAD_INFORMATION"
author: windows-driver-content
description: Stores xHCI-specific information that is used by client drivers to transfer data to and from the offloaded endpoints.
old-location: buses\usbd_endpoint_offload_information.htm
old-project: usbref
ms.assetid: F2A8E966-269E-447F-9467-EB2E877FFAA2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usb/USBD_ENDPOINT_OFFLOAD_INFORMATION, _USBD_ENDPOINT_OFFLOAD_INFORMATION, buses.usbd_endpoint_offload_information, PUSBD_ENDPOINT_OFFLOAD_INFORMATION, *PUSBD_ENDPOINT_OFFLOAD_INFORMATION, USBD_ENDPOINT_OFFLOAD_INFORMATION structure [Buses], usb/PUSBD_ENDPOINT_OFFLOAD_INFORMATION, USBD_ENDPOINT_OFFLOAD_INFORMATION, PUSBD_ENDPOINT_OFFLOAD_INFORMATION structure pointer [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usb.h
apiname:
-	USBD_ENDPOINT_OFFLOAD_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PUSBD_ENDPOINT_OFFLOAD_INFORMATION, USBD_ENDPOINT_OFFLOAD_INFORMATION"
req.product: Windows 10 or later.
---

# _USBD_ENDPOINT_OFFLOAD_INFORMATION structure
Stores xHCI-specific information that is used by client drivers to transfer data to and from the offloaded endpoints.

## Syntax
````
typedef struct _USBD_ENDPOINT_OFFLOAD_INFORMATION {
  ULONG                       Size;
  USHORT                      EndpointAddress;
  ULONG                       ResourceId;
  USBD_ENDPOINT_OFFLOAD_MODE  Mode;
  ULONG                       RootHubPortNumber  :8;
  ULONG                       RouteString  :20;
  ULONG                       Speed  :4;
  ULONG                       UsbDeviceAddress  :8;
  ULONG                       SlotId  :8;
  ULONG                       MultiTT  :1;
  ULONG                       Reserved0  :15;
  TransferSegmentLA           PHYSICAL_ADDRESS;
  TransferSegmentVA           PVOID;
  TransferRingSize            size_t;
  TransferRingInitialCycleBit ULONG;
  MessageNumber               ULONG;
  EventRingSegmentLA          PHYSICAL_ADDRESS;
  EventRingSegmentVA          PVOID;
  EventRingSize               size_t;
  EventRingInitialCycleBit    ULONG;
} USBD_ENDPOINT_OFFLOAD_INFORMATION, *PUSBD_ENDPOINT_OFFLOAD_INFORMATION;
````

## Members


`EndpointAddress`

Specifies the USB-defined endpoint address.

`EventRingInitialCycleBit`



`EventRingSegmentLA`



`EventRingSegmentVA`



`EventRingSize`



`MessageNumber`



`Mode`

A <a href="..\usb\ne-usb-_usbd_endpoint_offload_mode.md">USBD_ENDPOINT_OFFLOAD_MODE</a>-type value that indicates whether endpoint offloading is handled in software or the USB device or host controller.

`MultiTT`

Transaction Translator (TT) hub.

`Reserved0`

Reserved.

`ResourceId`

The resource identifier.

`RootHubPortNumber`

The port number of the root hub.

`RouteString`

The route string.

`Size`

The size of this structure.

`SlotId`

The slot identifier.

`Speed`

The route string.

`TransferRingInitialCycleBit`



`TransferRingSize`



`TransferSegmentLA`



`TransferSegmentVA`



`UsbDeviceAddress`

The USB device address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | usb.h |