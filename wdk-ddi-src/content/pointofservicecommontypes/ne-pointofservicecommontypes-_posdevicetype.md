---
UID: NE:pointofservicecommontypes._PosDeviceType
title: _PosDeviceType
author: windows-driver-content
description: This enumeration defines values used in the PosDeviceBasicsType structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader).
old-location: pos\posdevicetype.htm
old-project: pos
ms.assetid: 1e0b4b66-f9aa-4315-a07d-b6fd47f10371
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PosDeviceType, PosDeviceType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosDeviceType
req.alt-loc: pointofservicecommontypes.h
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
req.typenames: PosDeviceType
---

# _PosDeviceType enumeration



## -description
This enumeration defines values used in the <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posdevicebasicstype.md">PosDeviceBasicsType</a> structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader). 



## -syntax

````
typedef enum _PosDeviceType { 
  PosDeviceType_Unknown               = 0,
  PosDeviceType_BarcodeScanner        = 1,
  PosDeviceType_MagneticStripeReader  = 2,
  PosDeviceType_Printer               = 3,
  PosDeviceType_CashDrawer            = 4,
  PosDeviceType_Max                   = 5
} PosDeviceType;
````


## -enum-fields

### -field PosDeviceType_Unknown

Indicates that the type of device is not known.


### -field PosDeviceType_BarcodeScanner

Indicates that the type of device is a barcode scanner.


### -field PosDeviceType_MagneticStripeReader

Indicates that the type of device is a magnetic stripe reader.


### -field PosDeviceType_Printer

Indicates that the type of device is a printer.


### -field PosDeviceType_CashDrawer

Indicates that the type of device is a cash drawer.


### -field PosDeviceType_Max

Unused.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pointofservicecommontypes.h (include Pointofservicecommontypes.h)</dt>
</dl>
</td>
</tr>
</table>