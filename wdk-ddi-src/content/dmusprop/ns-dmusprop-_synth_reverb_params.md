---
UID: NS.DMUSPROP._SYNTH_REVERB_PARAMS
title: _SYNTH_REVERB_PARAMS
author: windows-driver-content
description: The SYNTH_REVERB_PARAMS structure contains configuration parameters.
old-location: audio\synth_reverb_params.htm
old-project: audio
ms.assetid: 9537D56C-920E-478E-9061-C4909240D7A0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYNTH_REVERB_PARAMS, SYNTH_REVERB_PARAMS, *PSYNTH_REVERB_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SYNTH_REVERB_PARAMS
req.alt-loc: Dmusprop.h
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
---

# _SYNTH_REVERB_PARAMS structure



## -description
The SYNTH_REVERB_PARAMS structure contains configuration parameters.


## -syntax

````
typedef struct _SYNTH_REVERB_PARAMS {
  float fInGain;
  float fReverbMix;
  float fReverbTime;
  float fHighFreqRTRatio;
} SYNTH_REVERB_PARAMS, *PSYNTH_REVERB_PARAMS;
````


## -struct-fields

### -field fInGain

Specifies the input gain in decibels (dB) to avoid output overflows.

### -field fReverbMix

Specifies the reverb mix in dB. 0dB specifies 100% wet reverb (no direct signal). Negative values specify a less wet signal. The coefficients are calculated so that the overall output level stays approximately constant regardless of the amount of reverb mix. 

### -field fReverbTime

Specifies the reverb delay time in milliseconds.

### -field fHighFreqRTRatio

Specifies the ratio of the high frequencies to the global reverb time. Unless very 'splashy-bright' reverberations are desired, this should be set to a value less than 1.0. For example, if <b>dRevTime</b> is 1000ms and HHighFreqRTRatio is 0.1, then the decay time for high frequencies will be 100ms.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dmusprop.h</dt>
</dl>
</td>
</tr>
</table>