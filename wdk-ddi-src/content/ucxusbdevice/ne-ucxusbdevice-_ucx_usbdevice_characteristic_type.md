---
UID: NE.ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC_TYPE
title: _UCX_USBDEVICE_CHARACTERISTIC_TYPE
author: windows-driver-content
description: Defines values that indicates the type of device characteristic.
old-location: buses\ucx_usbdevice_characteristic_type.htm
old-project: usbref
ms.assetid: 86FA72CC-C23F-40B9-9FDD-80C3B0D5EA73
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_USBDEVICE_CHARACTERISTIC_TYPE, UCX_USBDEVICE_CHARACTERISTIC_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_USBDEVICE_CHARACTERISTIC_TYPE
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
req.irql: DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration



## -description
Defines values that indicates the type of device characteristic.



## -syntax

````
typedef enum _UCX_USBDEVICE_CHARACTERISTIC_TYPE { 
  UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY  = 0x01
} UCX_USBDEVICE_CHARACTERISTIC_TYPE, *PUCX_USBDEVICE_CHARACTERISTIC_TYPE;
````


## -enum-fields

### -field UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY

The type of characteristic of the device.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
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

## -see-also
<dl>
<dt>
<a href="buses.ucx_usbdevice_characteristic">UCX_USBDEVICE_CHARACTERISTIC</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

