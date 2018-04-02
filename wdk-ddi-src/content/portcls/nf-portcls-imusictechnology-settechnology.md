---
UID: NF:portcls.IMusicTechnology.SetTechnology
title: IMusicTechnology::SetTechnology method
author: windows-driver-content
description: The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins.
old-location: audio\imusictechnology_settechnology.htm
old-project: audio
ms.assetid: 7e32b408-930d-4ef4-960e-1a0da5ef6803
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMusicTechnology, IMusicTechnology interface [Audio Devices], SetTechnology method, IMusicTechnology::SetTechnology, SetTechnology method [Audio Devices], SetTechnology method [Audio Devices], IMusicTechnology interface, SetTechnology,IMusicTechnology.SetTechnology, audio.imusictechnology_settechnology, audmp-routines_d1d6abaa-c4b8-4dce-8ce5-9fc12cc87852.xml, portcls/IMusicTechnology::SetTechnology
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
-	COM
api_location:
-	portcls.h
api_name:
-	IMusicTechnology.SetTechnology
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IMusicTechnology::SetTechnology method
The <code>SetTechnology</code> method changes the <b>Technology</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff537097">KSDATARANGE_MUSIC</a> structure in the data ranges for the miniport driver's pins.

## Syntax

```
NTSTATUS SetTechnology(
  const GUID *Technology
);
```

## Parameters

`Technology`

Specifies a technology GUID. This parameter should point to one of the GUIDs that are defined for the <b>Technology</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537097">KSDATARANGE_MUSIC</a> structure.


## Return Value

<code>SetTechnology</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The <code>SetTechology</code> method should be called before the miniport driver's <b>Init</b> method. If <code>SetTechnology</code> is not called, the miniport driver's <b>Technology</b> members are all set to KSMUSIC_TECHNOLOGY_PORT by default.

The following table lists the GUIDs that are defined for the <i>Technology</i> parameter and the corresponding integer value to which the <b>wTechnology</b> member of the MIDIOUTCAPS structure is set during a call to <b>midiOutGetDevCaps</b>.

<table>
<tr>
<th>Technology GUID</th>
<th>MIDIOUTCAPS.wTechnology</th>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_PORT

</td>
<td>
MOD_MIDIPORT

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_SQSYNTH

</td>
<td>
MOD_SQSYNTH

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_FMSYNTH 

</td>
<td>
MOD_FMSYNTH

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_WAVETABLE

</td>
<td>
MOD_WAVETABLE

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_SWSYNTH

</td>
<td>
MOD_SWSYNTH

</td>
</tr>
</table>
 

For more information, see <a href="https://msdn.microsoft.com/3b7c2907-e67f-458e-809d-080dcc30be1a">Music Technology GUIDs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536778">IMusicTechnology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537097">KSDATARANGE_MUSIC</a>