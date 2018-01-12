---
UID: NS:ntddcdrm._CDROM_PLAY_AUDIO_MSF
title: _CDROM_PLAY_AUDIO_MSF
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD.
old-location: storage\cdrom_play_audio_msf.htm
old-project: storage
ms.assetid: 73589397-9b2b-4d49-9860-cb2eb6a26632
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_PLAY_AUDIO_MSF, CDROM_PLAY_AUDIO_MSF, *PCDROM_PLAY_AUDIO_MSF
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
req.alt-api: CDROM_PLAY_AUDIO_MSF
req.alt-loc: ntddcdrm.h
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
req.typenames: CDROM_PLAY_AUDIO_MSF, *PCDROM_PLAY_AUDIO_MSF
---

# _CDROM_PLAY_AUDIO_MSF structure



## -description
Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_play_audio_msf.md">IOCTL_CDROM_PLAY_AUDIO_MSF</a> use this structure to play an audio CD.



## -syntax

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


## -struct-fields

### -field StartingM

Contains an integer between 0 and 74 that indicates the starting minute. 


### -field StartingS

Contains an integer between 0 and 59 that indicates the starting second. 


### -field StartingF

Contains an integer between 0 and 74 that indicates the starting frame. 


### -field EndingM

Contains an integer between 0 and 74 that indicates the ending minute. 


### -field EndingS

Contains an integer between 0 and 59 that indicates the ending second. 


### -field EndingF

Contains an integer between 0 and 74 that indicates the ending frame.


## -remarks
Device control IRPs with a control code of IOCTL_CDROM_PLAY_AUDIO_MSF use this structure to play an audio CD and to indicate where to begin playing and where to stop. Starting and ending points are indicated in terms of minutes, seconds, and frames.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_play_audio_msf.md">IOCTL_CDROM_PLAY_AUDIO_MSF</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PLAY_AUDIO_MSF structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

