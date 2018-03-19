---
UID: NS:ksmedia.KSAUDIO_POSITIONEX
title: KSAUDIO_POSITIONEX
author: windows-driver-content
description: The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.
old-location: audio\ksaudio_positionex.htm
old-project: audio
ms.assetid: 63cd938c-1ccd-4f67-a4eb-2898002ae762
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX, KSAUDIO_POSITIONEX structure [Audio Devices], PKSAUDIO_POSITIONEX, PKSAUDIO_POSITIONEX structure pointer [Audio Devices], aud-prop_9a418d76-9a4f-4626-b6db-64ed4fcedb18.xml, audio.ksaudio_positionex, ksmedia/KSAUDIO_POSITIONEX, ksmedia/PKSAUDIO_POSITIONEX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	ksmedia.h
api_name:
-	KSAUDIO_POSITIONEX
product: Windows
targetos: Windows
req.typenames: KSAUDIO_POSITIONEX, *PKSAUDIO_POSITIONEX
---

# KSAUDIO_POSITIONEX structure
The KSAUDIO_POSITIONEX structure specifies the stream position and the associated timestamp information for a kernel streaming (KS)-based audio driver.

## Syntax
````
typedef struct {
  LARGE_INTEGER    TimerFrequency;
  LARGE_INTEGER    TimeStamp1;
  KSAUDIO_POSITION Position;
  LARGE_INTEGER    TimeStamp2;
} KSAUDIO_POSITIONEX, *PKSAUDIO_POSITIONEX;
````

## Members


`TimerFrequency`

Specifies the number of ticks per second for the timer that produces the timestamps.

`TimeStamp1`

Specifies the timestamp that is taken immediately prior to the acquisition of the position information.

`Position`

Specifies the position of the read cursor and the write cursor in the audio buffer of an audio stream.

`TimeStamp2`

Specifies the timestamp that is taken immediately after the acquisition of the position information.

## Remarks
A KS-based audio driver can use the KSAUDIO_POSITIONEX structure along with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537298">KSPROPERTY_AUDIO_POSITIONEX</a> property to return a stream position and a timestamp.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows. Available in Windows Vista and later versions of Windows. |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537298">KSPROPERTY_AUDIO_POSITIONEX</a>