---
UID: NS.KSMEDIA.TAGKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
title: tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
author: windows-driver-content
description: This structure contains the capabilities for an ROI control.
old-location: stream\kscamera_extendedprop_roi_configcaps.htm
old-project: stream
ms.assetid: BAC5B134-22F5-4BC9-BBD6-6AF3C934510B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
req.alt-loc: Ksmedia.h
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
---

# tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure



## -description
This structure contains the capabilities for an ROI control.



## -syntax

````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS {
  ULONG     ControlId;
  ULONG     MaxNumberOfROIs;
  ULONGLONG Capability;
} KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS;
````


## -struct-fields

### -field ControlId

The ISP control ID. The following are valid values for this field. These values are defined in ksmedia.h.

<ul>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE

</li>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE

</li>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE

</li>
</ul>

### -field MaxNumberOfROIs

The maximum ROIs supported for this ISO control.


### -field Capability

The capabilities for this ISP control.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>