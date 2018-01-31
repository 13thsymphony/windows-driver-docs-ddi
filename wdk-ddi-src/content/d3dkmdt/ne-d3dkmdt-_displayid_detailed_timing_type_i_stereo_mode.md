---
UID : NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE
title : "_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE"
author : windows-driver-content
description : The DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration indicates the display device's stereo vision mode.
old-location : display\displayid_detailed_timing_type_i_stereo_mode.htm
old-project : display
ms.assetid : 7e40ddf4-0098-4ea6-ab93-17515849b6cd
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dkmdt/DIDDT1_Monoscopic, display.displayid_detailed_timing_type_i_stereo_mode, d3dkmdt/_DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE, _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE, _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration [Display Devices], DIDDT1_Dependent, d3dkmdt/DIDDT1_Stereo, DIDDT1_Stereo, d3dkmdt/DIDDT1_Dependent, DIDDT1_Monoscopic, DmEnums_011fdd6c-ba90-40f7-ad26-d1fe075d21c3.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE Enumeration
The DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE enumeration indicates the display device's stereo vision mode.

## Syntax
````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE {
  DIDDT1_Monoscopic  = 0, 
  DIDDT1_Stereo      = 1, 
  DIDDT1_Dependent   = 2 

};
````

## Constants

<table>

<tr>
<td>DIDDT1_Dependent</td>
<td>Indicates that the mode depends upon user action.</td>
</tr>

<tr>
<td>DIDDT1_Monoscopic</td>
<td>Indicates monoscopic mode (no stereo vision).</td>
</tr>

<tr>
<td>DIDDT1_Stereo</td>
<td>Indicates stereo mode.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |