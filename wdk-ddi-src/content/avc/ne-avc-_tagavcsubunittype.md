---
UID: NE.avc._tagAvcSubunitType
title: _tagAvcSubunitType
author: windows-driver-content
description: The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit.
old-location: stream\avcsubunittype.htm
old-project: stream
ms.assetid: c99db45c-2d99-4bf7-98f8-4d9501ac81c0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _tagAvcSubunitType, AvcSubunitType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AvcSubunitType
req.alt-loc: avc.h
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
---

# _tagAvcSubunitType enumeration



## -description
The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit.



## -syntax

````
typedef enum _tagAvcSubunitType { 
  AVC_SUBUNITTYPE_VIDEO_MONITOR  = 0x00,
  AVC_SUBUNITTYPE_AUDIO          = 0x01,
  AVC_SUBUNITTYPE_PRINTER        = 0x02,
  AVC_SUBUNITTYPE_DISC_PLAYER    = 0x03,
  AVC_SUBUNITTYPE_TAPE_PLAYER    = 0x04,
  AVC_SUBUNITTYPE_TUNER          = 0x05,
  AVC_SUBUNITTYPE_CA             = 0x06,
  AVC_SUBUNITTYPE_VIDEO_CAMERA   = 0x07,
  AVC_SUBUNITTYPE_PANEL          = 0x09,
  AVC_SUBUNITTYPE_BULLETINBOARD  = 0x0A,
  AVC_SUBUNITTYPE_CAMERASTORAGE  = 0x0B,
  AVC_SUBUNITTYPE_VENDOR_UNIQUE  = 0x1c,
  AVC_SUBUNITTYPE_EXTENDED       = 0x1e,
  AVC_SUBUNITTYPE_EXTENDED_FULL  = 0xff,
  AVC_SUBUNITTYPE_UNIT           = 0x1f
} AvcSubunitType;
````


## -enum-fields

### -field AVC_SUBUNITTYPE_VIDEO_MONITOR

Specifies a video monitor subunit type.


### -field AVC_SUBUNITTYPE_AUDIO

Specifies an audio subunit type.


### -field AVC_SUBUNITTYPE_PRINTER

Specifies a printer subunit type.


### -field AVC_SUBUNITTYPE_DISC_PLAYER

Specifies a disc player subunit type.


### -field AVC_SUBUNITTYPE_TAPE_PLAYER

Specifies a tape player subunit type.


### -field AVC_SUBUNITTYPE_TUNER

Specifies a tuner subunit type.


### -field AVC_SUBUNITTYPE_CA

Specifies a conditional access (CA) subunit type.


### -field AVC_SUBUNITTYPE_VIDEO_CAMERA

Specifies a video camera subunit type.


### -field AVC_SUBUNITTYPE_PANEL

Specifies a panel subunit type.


### -field AVC_SUBUNITTYPE_BULLETINBOARD

Specifies a bulletin board subunit type.


### -field AVC_SUBUNITTYPE_CAMERASTORAGE

Specifies a camera storage subunit type.


### -field AVC_SUBUNITTYPE_VENDOR_UNIQUE

Specifies a vendor unique subunit type.


### -field AVC_SUBUNITTYPE_EXTENDED

Specifies an extended subunit type.


### -field AVC_SUBUNITTYPE_EXTENDED_FULL

This is used only in extension bytes


### -field AVC_SUBUNITTYPE_UNIT

Specifies a generic subunit type.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>