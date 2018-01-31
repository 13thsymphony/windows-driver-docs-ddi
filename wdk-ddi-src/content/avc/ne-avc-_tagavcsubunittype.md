---
UID : NE:avc._tagAvcSubunitType
title : "_tagAvcSubunitType"
author : windows-driver-content
description : The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit.
old-location : stream\avcsubunittype.htm
old-project : stream
ms.assetid : c99db45c-2d99-4bf7-98f8-4d9501ac81c0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : AVC_SUBUNITTYPE_VIDEO_MONITOR, AVC_SUBUNITTYPE_PANEL, AVC_SUBUNITTYPE_BULLETINBOARD, avc/AVC_SUBUNITTYPE_EXTENDED_FULL, AVC_SUBUNITTYPE_TAPE_PLAYER, avc/AVC_SUBUNITTYPE_BULLETINBOARD, avc/AVC_SUBUNITTYPE_EXTENDED, AVC_SUBUNITTYPE_TUNER, AVC_SUBUNITTYPE_DISC_PLAYER, AVC_SUBUNITTYPE_UNIT, AVC_SUBUNITTYPE_AUDIO, _tagAvcSubunitType, AVC_SUBUNITTYPE_CA, avc/AVC_SUBUNITTYPE_VIDEO_MONITOR, avc/AVC_SUBUNITTYPE_PANEL, AVC_SUBUNITTYPE_PRINTER, avc/AVC_SUBUNITTYPE_VENDOR_UNIQUE, avc/AVC_SUBUNITTYPE_TUNER, AvcSubunitType enumeration [Streaming Media Devices], avc/AVC_SUBUNITTYPE_CA, AVC_SUBUNITTYPE_VENDOR_UNIQUE, avc/AVC_SUBUNITTYPE_UNIT, avc/AVC_SUBUNITTYPE_AUDIO, AVC_SUBUNITTYPE_EXTENDED, avc/AVC_SUBUNITTYPE_TAPE_PLAYER, stream.avcsubunittype, avc/AvcSubunitType, avc/AVC_SUBUNITTYPE_PRINTER, avc/AVC_SUBUNITTYPE_CAMERASTORAGE, avc/AVC_SUBUNITTYPE_VIDEO_CAMERA, AVC_SUBUNITTYPE_CAMERASTORAGE, AVC_SUBUNITTYPE_EXTENDED_FULL, AvcSubunitType, AVC_SUBUNITTYPE_VIDEO_CAMERA, avc/AVC_SUBUNITTYPE_DISC_PLAYER, avcref_e6283b0f-7f87-4c6b-aedf-c8e8762e7098.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : avc.h
req.include-header : Avc.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : AvcSubunitType
---

# _tagAvcSubunitType Enumeration
The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit.

## Syntax
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

## Constants

<table>

<tr>
<td>AVC_SUBUNITTYPE_AUDIO</td>
<td>Specifies an audio subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_BULLETINBOARD</td>
<td>Specifies a bulletin board subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_CA</td>
<td>Specifies a conditional access (CA) subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_CAMERASTORAGE</td>
<td>Specifies a camera storage subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_DISC_PLAYER</td>
<td>Specifies a disc player subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_EXTENDED</td>
<td>Specifies an extended subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_EXTENDED_FULL</td>
<td>This is used only in extension bytes</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_PANEL</td>
<td>Specifies a panel subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_PRINTER</td>
<td>Specifies a printer subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_TAPE_PLAYER</td>
<td>Specifies a tape player subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_TUNER</td>
<td>Specifies a tuner subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_UNIT</td>
<td>Specifies a generic subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_VENDOR_UNIQUE</td>
<td>Specifies a vendor unique subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_VIDEO_CAMERA</td>
<td>Specifies a video camera subunit type.</td>
</tr>

<tr>
<td>AVC_SUBUNITTYPE_VIDEO_MONITOR</td>
<td>Specifies a video monitor subunit type.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | avc.h (include Avc.h) |