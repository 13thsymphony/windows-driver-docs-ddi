---
UID: NS:hdaudio._HDAUDIO_DEVICE_INFORMATION
title: "_HDAUDIO_DEVICE_INFORMATION"
author: windows-driver-content
description: The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.
old-location: audio\hdaudio_device_information.htm
old-project: audio
ms.assetid: 091aee9d-5ecd-481a-b5e2-28b4828b2c2e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PHDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION structure [Audio Devices], PHDAUDIO_DEVICE_INFORMATION, PHDAUDIO_DEVICE_INFORMATION structure pointer [Audio Devices], _HDAUDIO_DEVICE_INFORMATION, aud-prop2_3350e3d4-dfbe-4002-b237-2395f4a07c7f.xml, audio.hdaudio_device_information, hdaudio/HDAUDIO_DEVICE_INFORMATION, hdaudio/PHDAUDIO_DEVICE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hdaudio.h
api_name:
-	HDAUDIO_DEVICE_INFORMATION
product: Windows
targetos: Windows
req.typenames: HDAUDIO_DEVICE_INFORMATION, *PHDAUDIO_DEVICE_INFORMATION
---

# _HDAUDIO_DEVICE_INFORMATION structure
The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.

## Syntax
````
typedef struct _HDAUDIO_DEVICE_INFORMATION {
  USHORT  Size;
  USHORT  DeviceVersion;
  USHORT  DriverVersion;
  USHORT  CodecsDetected;
  BOOLEAN IsStripingSupported;
} HDAUDIO_DEVICE_INFORMATION, *PHDAUDIO_DEVICE_INFORMATION;
````

## Members


`Size`

Specifies the size in bytes of the HDAUDIO_DEVICE_INFORMATION structure.

`DeviceVersion`

Specifies the HD Audio controller device version.

`DriverVersion`

Specifies the HD Audio bus driver version.

`CodecsDetected`

Specifies the number of codecs that the HD Audio controller detects on the HD Audio Link.

`IsStripingSupported`

Specifies whether the HD Audio controller supports <a href="https://msdn.microsoft.com/29ab650c-0c3b-4693-a277-4d9ba63b7b66">striping</a>. If <b>TRUE</b>, it supports striping (with at least two SDO lines). If <b>FALSE</b>, it does not support striping.

## Remarks
The <a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a> routine uses this structure to provide information about the HD Audio controller's device-specific capabilities to clients.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hdaudio.h (include Hdaudio.h) |

## See Also

<a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a>