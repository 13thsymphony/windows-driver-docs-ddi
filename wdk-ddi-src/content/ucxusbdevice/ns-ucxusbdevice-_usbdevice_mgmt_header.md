---
UID: NS:ucxusbdevice._USBDEVICE_MGMT_HEADER
title: "_USBDEVICE_MGMT_HEADER"
author: windows-driver-content
description: This structure provides a handle for the Universal Serial Bus (USB) hub or device physically connected to the bus.
old-location: buses\_usbdevice_mgmt_header.htm
old-project: usbref
ms.assetid: E3CDED41-FE83-4CBC-9FF8-4858125F7108
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_USBDEVICE_MGMT_HEADER, P_USBDEVICE_MGMT_HEADER structure pointer [Buses], USBDEVICE_MGMT_HEADER, ucxusbdevice/P_USBDEVICE_MGMT_HEADER, USBDEVICE_MGMT_HEADER structure [Buses], P_USBDEVICE_MGMT_HEADER, ucxusbdevice/_USBDEVICE_MGMT_HEADER, *PUSBDEVICE_MGMT_HEADER, buses._usbdevice_mgmt_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxusbdevice.h
apiname:
-	USBDEVICE_MGMT_HEADER
product: Windows
targetos: Windows
req.typenames: USBDEVICE_MGMT_HEADER, *PUSBDEVICE_MGMT_HEADER
req.product: Windows 10 or later.
---

# _USBDEVICE_MGMT_HEADER structure
This structure provides a handle  for the Universal Serial Bus (USB) hub or device physically connected to the bus.

## Syntax
````
typedef struct _USBDEVICE_MGMT_HEADER {
  ULONG        Size;
  UCXUSBDEVICE Hub;
  UCXUSBDEVICE UsbDevice;
} USBDEVICE_MGMT_HEADER, *P_USBDEVICE_MGMT_HEADER;
````

## Members


`Hub`

The handle to the USB hub that is physically connected to the bus.

`Size`

The size in bytes of this structure.

`UsbDevice`

The handle for the USB device that is physically connected to the bus.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |