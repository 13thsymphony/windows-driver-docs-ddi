---
UID : NS:ksmedia.KSDS3D_HRTF_INIT_MSG
title : KSDS3D_HRTF_INIT_MSG
author : windows-driver-content
description : The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF).
old-location : audio\ksds3d_hrtf_init_msg.htm
old-project : audio
ms.assetid : 8e25a1e2-24b1-418c-b1eb-884bdbad63b3
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : aud-prop_f9994a16-7d3c-43af-b423-c6afc64c05b9.xml, ksmedia/KSDS3D_HRTF_INIT_MSG, KSDS3D_HRTF_INIT_MSG structure [Audio Devices], KSDS3D_HRTF_INIT_MSG, PKSDS3D_HRTF_INIT_MSG structure pointer [Audio Devices], audio.ksds3d_hrtf_init_msg, ksmedia/PKSDS3D_HRTF_INIT_MSG, PKSDS3D_HRTF_INIT_MSG, *PKSDS3D_HRTF_INIT_MSG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
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
req.typenames : KSDS3D_HRTF_INIT_MSG, *PKSDS3D_HRTF_INIT_MSG
---

# KSDS3D_HRTF_INIT_MSG structure
The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF).

## Syntax
````
typedef struct {
  ULONG                      Size;
  KSDS3D_HRTF_FILTER_QUALITY Quality;
  FLOAT                      SampleRate;
  ULONG                      MaxFilterSize;
  ULONG                      FilterTransientMuteLength;
  ULONG                      FilterOverlapBufferLength;
  ULONG                      OutputOverlapBufferLength;
  ULONG                      Reserved;
} KSDS3D_HRTF_INIT_MSG, *PKSDS3D_HRTF_INIT_MSG;
````

## Members


`FilterOverlapBufferLength`

Specifies the total number of samples over which to mute and cross-fade the filter outputs.

`FilterTransientMuteLength`

Specifies how long to delay cross-fading to the new filter in order to avoid introducing the new filter's initial transient signal into the output signal. The delay is specified as a number of initial samples produced by the new filter. During this time, the output comes from the old filters only.

`MaxFilterSize`

Specifies the maximum filter size in bytes. If the filter is in direct form, the maximum size is the order of the filter (numerator and denominator have equal order). If the filter is in cascade form, the maximum size is the maximum number of biquadratic coefficients.

`OutputOverlapBufferLength`

Specifies the number of samples over which to cross-fade the output channels after a transition across azimuth angle zero. This member is used when cross-fading of the output channels is enabled by the <b>CrossFadeOutput</b> member of <a href="..\ksmedia\ns-ksmedia-ksds3d_hrtf_params_msg.md">KSDS3D_HRTF_PARAMS_MSG</a>.

`Quality`

Specifies the HRTF filter quality level. Set this parameter to one of the following KSDS3D_HRTF_FILTER_QUALITY enumeration values:
<ul>
<li>
LIGHT_FILTER selects an efficient algorithm that produces a good quality effect.

</li>
<li>
FULL_FILTER selects an algorithm that produces a high-quality effect but requires more processing time.

</li>
</ul>

`Reserved`

Reserved. Set to zero.

`SampleRate`

Specifies the sample rate, in samples per second (hertz), at which each channel should be played. For example, a value of 22,050 specifies a sample rate of 22.05 kHz.

`Size`

Specifies the size in bytes of the structure.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537355">KSPROPERTY_HRTF3D_INITIALIZE</a> property.

The <b>Quality</b> values FULL_FILTER and LIGHT_FILTER correspond to the GUID_DS3DALG_HRTF_FULL and GUID_DS3DALG_HRTF_LIGHT settings that are described in the Microsoft Windows SDK documentation.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537355">KSPROPERTY_HRTF3D_INITIALIZE</a>

<a href="..\ksmedia\ns-ksmedia-ksds3d_hrtf_params_msg.md">KSDS3D_HRTF_PARAMS_MSG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_HRTF_INIT_MSG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>