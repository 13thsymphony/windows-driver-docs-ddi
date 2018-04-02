---
UID: NS:ksmedia.KSDS3D_HRTF_PARAMS_MSG
title: KSDS3D_HRTF_PARAMS_MSG
author: windows-driver-content
description: The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_params_msg.htm
old-project: audio
ms.assetid: e746fc3d-ebfd-41a1-b640-6f803423bd95
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG structure [Audio Devices], PKSDS3D_HRTF_PARAMS_MSG, PKSDS3D_HRTF_PARAMS_MSG structure pointer [Audio Devices], aud-prop_1f9e726f-d9b6-43e5-8c6e-82e645587ca4.xml, audio.ksds3d_hrtf_params_msg, ksmedia/KSDS3D_HRTF_PARAMS_MSG, ksmedia/PKSDS3D_HRTF_PARAMS_MSG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KSDS3D_HRTF_PARAMS_MSG
product:
- Windows
targetos: Windows
req.typenames: KSDS3D_HRTF_PARAMS_MSG, *PKSDS3D_HRTF_PARAMS_MSG
---

# KSDS3D_HRTF_PARAMS_MSG structure
The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).

## Syntax
```
typedef struct KSDS3D_HRTF_PARAMS_MSG {
  ULONG Size;
  ULONG Enabled;
  BOOL  SwapChannels;
  BOOL  ZeroAzimuth;
  BOOL  CrossFadeOutput;
  ULONG FilterSize;
} *PKSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG;
```

## Members


`Size`

Specifies the size in bytes of the structure.

`Enabled`

Specifies whether to enable HRTF processing. If nonzero, HRTF is enabled. If zero, it is disabled.

`SwapChannels`

Specifies whether the algorithm should swap channels. If <b>TRUE</b>, the algorithm should swap the channels to perform a left-to-right reversal of the location of the source. If <b>FALSE</b>, the algorithm should not swap the channels.

`ZeroAzimuth`

Specifies whether the azimuth angle is zero. If <b>TRUE</b>, then only half of the filter coefficients are downloaded to the filter because the azimuth angle is zero. If <b>FALSE</b>, all the coefficients are downloaded.

`CrossFadeOutput`

Specifies whether to cross-fade the output channels after crossing azimuth angle zero. If <b>TRUE</b>, the algorithm should cross-fade the output channels. If <b>FALSE</b>, it should not cross-fade the channels.

`FilterSize`

Specifies the additional size in bytes of the filter coefficients that are appended to this structure.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a> property.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>