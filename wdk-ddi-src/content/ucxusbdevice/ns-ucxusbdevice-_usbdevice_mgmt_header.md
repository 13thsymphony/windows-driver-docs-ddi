---
UID: NS.UCXUSBDEVICE._USBDEVICE_MGMT_HEADER
title: _USBDEVICE_MGMT_HEADER
author: windows-driver-content
description: This structure provides a handle for the Universal Serial Bus (USB) hub or device physically connected to the bus.
old-location: buses\_usbdevice_mgmt_header.htm
old-project: usbref
ms.assetid: E3CDED41-FE83-4CBC-9FF8-4858125F7108
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBDEVICE_MGMT_HEADER, USBDEVICE_MGMT_HEADER, *PUSBDEVICE_MGMT_HEADER
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
req.alt-api: USBDEVICE_MGMT_HEADER
req.alt-loc: ucxusbdevice.h
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

# _USBDEVICE_MGMT_HEADER structure



## -description
This structure provides a handle  for the Universal Serial Bus (USB) hub or device physically connected to the bus.


## -syntax

````
typedef struct _USBDEVICE_MGMT_HEADER {
  ULONG        Size;
  UCXUSBDEVICE Hub;
  UCXUSBDEVICE UsbDevice;
} USBDEVICE_MGMT_HEADER, *P_USBDEVICE_MGMT_HEADER;
````


## -struct-fields

### -field Size

The size in bytes of this structure.

### -field Hub

The handle to the USB hub that is physically connected to the bus.

### -field UsbDevice

The handle for the USB device that is physically connected to the bus.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>