---
UID: NE.hdaudio._HDAUDIO_CODEC_POWER_STATE
title: _HDAUDIO_CODEC_POWER_STATE
author: windows-driver-content
description: The HDAUDIO_CODEC_POWER_STATE enumeration defines constants that specify the different power states that HD Audio codecs can support. All states are from DEVICE_POWER_STATE except PowerCodecD3Cold.
old-location: audio\hdaudio_codec_power_state.htm
old-project: audio
ms.assetid: 4C002B40-AD27-4FE2-B07F-5E9715E6CF1F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HDAUDIO_CODEC_POWER_STATE, *PHDAUDIO_CODEC_POWER_STATE, HDAUDIO_CODEC_POWER_STATE, PHDAUDIO_CODEC_POWER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: hdaudio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_CODEC_POWER_STATE
req.alt-loc: Hdaudio.h
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
---

# _HDAUDIO_CODEC_POWER_STATE enumeration



## -description
The <b>HDAUDIO_CODEC_POWER_STATE</b> enumeration defines constants that specify the different power states that HD Audio codecs can support.  All states
are from <a href="kernel.device_power_state">DEVICE_POWER_STATE</a> except PowerCodecD3Cold.




## -syntax

````
typedef enum _HDAUDIO_CODEC_POWER_STATE { 
  PowerCodecUnspecified   = 0,
  PowerCodecD0,
  PowerCodecD1,
  PowerCodecD2,
  PowerCodecD3,
  PowerCodecD3Cold,
  PowerCodecMaximum
} HDAUDIO_CODEC_POWER_STATE, *PHDAUDIO_CODEC_POWER_STATE;
````


## -enum-fields

### -field PowerCodecUnspecified 

An unspecified power state.


### -field PowerCodecD0

Power state D0


### -field PowerCodecD1

Power state D1


### -field PowerCodecD2

Power state D2


### -field PowerCodecD3

Power state D3


### -field PowerCodecD3Cold

Power state D3 Cold


### -field PowerCodecMaximum

Power state Maximum


## -remarks
For more information about power states, see <a href="kernel.device_power_state">DEVICE_POWER_STATE</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hdaudio.h</dt>
</dl>
</td>
</tr>
</table>