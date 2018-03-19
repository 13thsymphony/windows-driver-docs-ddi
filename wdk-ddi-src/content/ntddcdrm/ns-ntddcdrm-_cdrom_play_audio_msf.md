---
UID: NS:ntddcdrm._CDROM_PLAY_AUDIO_MSF
title: "_CDROM_PLAY_AUDIO_MSF"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD.
old-location: storage\cdrom_play_audio_msf.htm
old-project: storage
ms.assetid: 73589397-9b2b-4d49-9860-cb2eb6a26632
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_PLAY_AUDIO_MSF, CDROM_PLAY_AUDIO_MSF, CDROM_PLAY_AUDIO_MSF structure [Storage Devices], PCDROM_PLAY_AUDIO_MSF, PCDROM_PLAY_AUDIO_MSF structure pointer [Storage Devices], _CDROM_PLAY_AUDIO_MSF, ntddcdrm/CDROM_PLAY_AUDIO_MSF, ntddcdrm/PCDROM_PLAY_AUDIO_MSF, storage.cdrom_play_audio_msf, structs-CD-ROM_27bfe732-1972-4101-baa1-e9d520c3dfcf.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	CDROM_PLAY_AUDIO_MSF
product: Windows
targetos: Windows
req.typenames: CDROM_PLAY_AUDIO_MSF, *PCDROM_PLAY_AUDIO_MSF
---

# _CDROM_PLAY_AUDIO_MSF structure
Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_play_audio_msf.md">IOCTL_CDROM_PLAY_AUDIO_MSF</a> use this structure to play an audio CD.

## Syntax
````
typedef struct _CDROM_PLAY_AUDIO_MSF {
  UCHAR StartingM;
  UCHAR StartingS;
  UCHAR StartingF;
  UCHAR EndingM;
  UCHAR EndingS;
  UCHAR EndingF;
} CDROM_PLAY_AUDIO_MSF, *PCDROM_PLAY_AUDIO_MSF;
````

## Members


`StartingM`

Contains an integer between 0 and 74 that indicates the starting minute.

`StartingS`

Contains an integer between 0 and 59 that indicates the starting second.

`StartingF`

Contains an integer between 0 and 74 that indicates the starting frame.

`EndingM`

Contains an integer between 0 and 74 that indicates the ending minute.

`EndingS`

Contains an integer between 0 and 59 that indicates the ending second.

`EndingF`

Contains an integer between 0 and 74 that indicates the ending frame.

## Remarks
Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD and to indicate where to begin playing and where to stop. Starting and ending points are indicated in terms of minutes, seconds, and frames.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_play_audio_msf.md">IOCTL_CDROM_PLAY_AUDIO_MSF</a>