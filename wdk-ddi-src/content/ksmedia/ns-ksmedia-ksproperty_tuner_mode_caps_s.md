---
UID: NS:ksmedia.KSPROPERTY_TUNER_MODE_CAPS_S
title: KSPROPERTY_TUNER_MODE_CAPS_S
author: windows-driver-content
description: The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.
old-location: stream\ksproperty_tuner_mode_caps_s.htm
old-project: stream
ms.assetid: e2376cde-7e13-475d-a118-0cf48ba8a742
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S, KSPROPERTY_TUNER_MODE_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_MODE_CAPS_S, PKSPROPERTY_TUNER_MODE_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_MODE_CAPS_S, ksmedia/PKSPROPERTY_TUNER_MODE_CAPS_S, stream.ksproperty_tuner_mode_caps_s, vidcapstruct_d80882b8-2962-48c3-b2e9-393deec31ccc.xml"
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
-	KSPROPERTY_TUNER_MODE_CAPS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_MODE_CAPS_S, *PKSPROPERTY_TUNER_MODE_CAPS_S
---

# KSPROPERTY_TUNER_MODE_CAPS_S structure
The KS_PROPERTY_TUNER_MODE_CAPS_S structure describes the capabilities of TV and radio tuner devices.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  ULONG      Mode;
  ULONG      StandardsSupported;
  ULONG      MinFrequency;
  ULONG      MaxFrequency;
  ULONG      TuningGranularity;
  ULONG      NumberOfInputs;
  ULONG      SettlingTime;
  ULONG      Strategy;
} KSPROPERTY_TUNER_MODE_CAPS_S, *PKSPROPERTY_TUNER_MODE_CAPS_S;
````

## Members


`Property`

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

`Mode`

Specifies the tuner mode that the caller is requesting capability information about. It can be one of the following tuner modes from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_TV

</td>
<td>
Indicates that the tuner is capable of tuning analog broadcast or cable television channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
Indicates that the tuner is capable of tuning AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
Indicates that the tuner is capable of tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
Indicates that the tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States) or other digital television standard.

</td>
</tr>
</table>

`StandardsSupported`

Describes the analog video standards supported. If <b>Mode</b> is set to KSPROPERTY_TUNER_MODE_TV, this member may be set to one or more (logically ORed) values from the <a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a> enumeration.

`MinFrequency`

Specifies the lowest frequency supported by the tuner. This value is in hertz (Hz).

`MaxFrequency`

Specifies the highest frequency supported by the tuner. This value is in hertz (Hz).

`TuningGranularity`

Specifies the smallest possible step size between two settings of the tuning frequency. This value is in hertz (Hz).

`NumberOfInputs`

Specifies the number of inputs on the tuner.

`SettlingTime`

Specifies the time, in milliseconds, for a new frequency setting to become stable.

`Strategy`

Specifies the tuning method. This member must be set to only one of the values from the <a href="..\ksmedia\ne-ksmedia-ks_tuner_strategy.md">KS_TUNER_STRATEGY</a> enumeration.

## Remarks
The minidriver fills in the mode capabilities for the requested tuner mode.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



<a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565865">KSPROPERTY_TUNER_MODE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="..\ksmedia\ne-ksmedia-ks_tuner_strategy.md">KS_TUNER_STRATEGY</a>