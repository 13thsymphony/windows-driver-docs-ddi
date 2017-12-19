---
UID: NS.UCXROOTHUB._ROOTHUB_30PORT_INFO_EX
title: _ROOTHUB_30PORT_INFO_EX
author: windows-driver-content
description: Provides extended USB 3.0 port information about speed.
old-location: buses\_roothub_30port_info_ex.htm
old-project: UsbRef
ms.assetid: 3FA3494F-DFFF-414E-B88C-DF7C034B96C6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ROOTHUB_30PORT_INFO_EX, ROOTHUB_30PORT_INFO_EX, *PROOTHUB_30PORT_INFO_EX, PROOTHUB_30PORT_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ROOTHUB_30PORT_INFO_EX
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _ROOTHUB_30PORT_INFO_EX structure



## -description
Provides extended USB 3.0 port information about  speed.



## -syntax

````
typedef struct _ROOTHUB_30PORT_INFO_EX {
#if __cplusplus
  ROOTHUB_30PORT_INFO                         Info;
#else 
  ROOTHUB_30PORT_INFO                         ;
#endif 
  USHORT                                      MaxSpeedsCount;
  USHORT                                      SpeedsCount;
  PUSB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED Speeds;
} ROOTHUB_30PORT_INFO_EX, *P_ROOTHUB_30PORT_INFO_EX;
````


## -struct-fields

### -field Info

A <a href="buses._roothub_30port_info">ROOTHUB_30PORT_INFO</a> structure.


### -field MaxSpeedsCount

Maximum number of speeds.


### -field SpeedsCount

The count of bus speeds supported.


### -field Speeds

A pointer to a <b>USB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED</b> structure that describes the USB 3.1capability's sublink speed attributes. For structure declaration, see Usbspec.h


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>