---
UID: NS:dmusprop._SYNTH_REVERB_PARAMS
title: "_SYNTH_REVERB_PARAMS"
author: windows-driver-content
description: The SYNTH_REVERB_PARAMS structure contains configuration parameters.
old-location: audio\synth_reverb_params.htm
old-project: audio
ms.assetid: 9537D56C-920E-478E-9061-C4909240D7A0
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: dmusprop/PSYNTH_REVERB_PARAMS, dmusprop/SYNTH_REVERB_PARAMS, *PSYNTH_REVERB_PARAMS, SYNTH_REVERB_PARAMS, PSYNTH_REVERB_PARAMS, audio.synth_reverb_params, SYNTH_REVERB_PARAMS structure [Audio Devices], _SYNTH_REVERB_PARAMS, PSYNTH_REVERB_PARAMS structure pointer [Audio Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dmusprop.h
apiname:
-	SYNTH_REVERB_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_REVERB_PARAMS, SYNTH_REVERB_PARAMS"
---

# _SYNTH_REVERB_PARAMS structure
The SYNTH_REVERB_PARAMS structure contains configuration parameters.

## Syntax
````
typedef struct _SYNTH_REVERB_PARAMS {
  float fInGain;
  float fReverbMix;
  float fReverbTime;
  float fHighFreqRTRatio;
} SYNTH_REVERB_PARAMS, *PSYNTH_REVERB_PARAMS;
````

## Members


`fHighFreqRTRatio`

Specifies the ratio of the high frequencies to the global reverb time. Unless very 'splashy-bright' reverberations are desired, this should be set to a value less than 1.0. For example, if <b>dRevTime</b> is 1000ms and HHighFreqRTRatio is 0.1, then the decay time for high frequencies will be 100ms.

`fInGain`

Specifies the input gain in decibels (dB) to avoid output overflows.

`fReverbMix`

Specifies the reverb mix in dB. 0dB specifies 100% wet reverb (no direct signal). Negative values specify a less wet signal. The coefficients are calculated so that the overall output level stays approximately constant regardless of the amount of reverb mix.

`fReverbTime`

Specifies the reverb delay time in milliseconds.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dmusprop.h |