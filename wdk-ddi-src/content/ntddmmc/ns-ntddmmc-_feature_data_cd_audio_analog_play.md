---
UID: NS:ntddmmc._FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
title: "_FEATURE_DATA_CD_AUDIO_ANALOG_PLAY"
author: windows-driver-content
description: The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.
old-location: storage\feature_data_cd_audio_analog_play.htm
old-project: storage
ms.assetid: 01c34bb8-b164-425d-b81c-7eefc08296e2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure [Storage Devices], PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure pointer [Storage Devices], _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, storage.feature_data_cd_audio_analog_play, structs-CD-ROM_87a067ea-0911-429b-808a-102f9600ecac.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY
---

# _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure
The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.

## Syntax
````
typedef struct _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY {
  FEATURE_HEADER Header;
  UCHAR          SeperateVolume  :1;
  UCHAR          SeperateChannelMute  :1;
  UCHAR          ScanSupported  :1;
  UCHAR          Reserved1  :5;
  UCHAR          Reserved2;
  UCHAR          NumerOfVolumeLevels[2];
} FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY;
````

## Members


`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`SeperateVolume`

Indicates, when set to zero, that all audio channels have the same volume level. When set to 1, it indicates that the volume of each audio channel can be set separately.

`SeperateChannelMute`

Indicates, when set to zero, that all audio channels are muted simultaneously. When set to 1, it indicates that each audio channel can be muted independently.

`ScanSupported`

Indicates, when set to 1, that the SCAN command is supported. See the <i>SCSI Multimedia 3 </i>(<i>MMC-3</i>) specification for a description of the SCAN command.

`Reserved1`

Reserved.

`Reserved2`

Reserved.

`NumerOfVolumeLevels`



## Remarks
This structure holds data for the feature named "CD Audio External Play" by the <i>MMC-3 </i>specification. Devices that support this feature can play CD audio data and channel it directly to an external output.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>