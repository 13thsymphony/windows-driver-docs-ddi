---
UID: NS.USBSCAN._DRV_VERSION
title: _DRV_VERSION
author: windows-driver-content
description: The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION.
old-location: image\drv_version.htm
old-project: Image
ms.assetid: 61b6dbd3-7565-4d63-bcc0-007df9793398
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DRV_VERSION, DRV_VERSION, *PDRV_VERSION, PDRV_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRV_VERSION
req.alt-loc: usbscan.h
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

# _DRV_VERSION structure



## -description
The DRV_VERSION structure is used as a parameter to <a href="base.deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_version.md">IOCTL_GET_VERSION</a>.



## -syntax

````
typedef struct _DRV_VERSION {
  unsigned major;
  unsigned minor;
  unsigned internal;
} DRV_VERSION, *PDRV_VERSION;
````


## -struct-fields

### -field major

Major version number.


### -field minor

Minor version number.


### -field internal

Internal, vendor-specific version number.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbscan.h (include Usbscan.h)</dt>
</dl>
</td>
</tr>
</table>