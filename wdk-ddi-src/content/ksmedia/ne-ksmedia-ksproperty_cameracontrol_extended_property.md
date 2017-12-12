---
UID: NE.ksmedia.KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY
title: KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY
author: windows-driver-content
description: This enumeration contains extended camera controls.
old-location: stream\ksproperty_cameracontrol_extended_property.htm
old-project: stream
ms.assetid: DA89A917-75F3-4120-90A4-8DA9DB322B4F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY, KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY
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

# KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY enumeration



## -description
This enumeration contains extended camera controls.



## -syntax

````
typedef enum  { 
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOFRAMERATE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMAXFRAMERATE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTRIGGERTIME,
  KSPROPERTY_CAMERACONTROL_EXTENDED_WARMSTART,
  KSPROPERTY_CAMERACONTROL_EXTENDED_MAXVIDFPS_PHOTORES,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTHUMBNAIL,
  KSPROPERTY_CAMERACONTROL_EXTENDED_SCENEMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_TORCHMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FLASHMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_OPTIMIZATIONHINT,
  KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ISO,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW,
  KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION,
  KSPROPERTY_CAMERACONTROL_EXTENDED_CAMERAANGLEOFFSET,
  KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSPRIORITY,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSSTATE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_CONFIGCAPS,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_ISPCONTROL,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOCONFIRMATION,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ISO_ADVANCED,
  KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOSTABILIZATION,
  KSPROPERTY_CAMERACONTROL_EXTENDED_VFR,
  KSPROPERTY_CAMERACONTROL_EXTENDED_FACEDETECTION,
  KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOHDR,
  KSPROPERTY_CAMERACONTROL_EXTENDED_HISTOGRAM,
  KSPROPERTY_CAMERACONTROL_EXTENDED_OIS,
  KSPROPERTY_CAMERACONTROL_EXTENDED_ADVANCEDPHOTO,
  KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE,
  KSPROPERTY_CAMERACONTROL_EXTENDED_END2
} KSPROPERTY_CAMERACONTROL_EXTENDED_PROPERTY;
````


## -enum-fields

### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE

  This enumerates  the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917959">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOFRAMERATE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567580">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOFRAMERATE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMAXFRAMERATE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567581">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMAXFRAMERATE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTRIGGERTIME

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567584">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTRIGGERTIME</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_WARMSTART

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567587">KSPROPERTY_CAMERACONTROL_EXTENDED_WARMSTART</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_MAXVIDFPS_PHOTORES

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567578">KSPROPERTY_CAMERACONTROL_EXTENDED_MAXVIDFPS_PHOTORES</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTHUMBNAIL

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567583">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOTHUMBNAIL</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_SCENEMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567585">KSPROPERTY_CAMERACONTROL_EXTENDED_SCENEMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_TORCHMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567586">KSPROPERTY_CAMERACONTROL_EXTENDED_TORCHMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FLASHMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917938">KSPROPERTY_CAMERACONTROL_EXTENDED_FLASHMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_OPTIMIZATIONHINT

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567579">KSPROPERTY_CAMERACONTROL_EXTENDED_OPTIMIZATIONHINT</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ISO

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567577">KSPROPERTY_CAMERACONTROL_EXTENDED_ISO</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567574">KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567572">KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_CAMERAANGLEOFFSET

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn567571">KSPROPERTY_CAMERACONTROL_EXTENDED_CAMERAANGLEOFFSET</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917952">KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSPRIORITY

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917942">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSPRIORITY</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSSTATE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917944">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSSTATE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_CONFIGCAPS

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917964">KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_CONFIGCAPS</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_ISPCONTROL

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917966">KSPROPERTY_CAMERACONTROL_EXTENDED_ROI_ISPCONTROL</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOCONFIRMATION

This enumerates the <a href="https://msdn.microsoft.com/library/windows/hardware/dn917957">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOCONFIRMATION</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn936756">KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ISO_ADVANCED

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917947">KSPROPERTY_CAMERACONTROL_EXTENDED_ISO_ADVANCED</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOSTABILIZATION

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn936754">KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOSTABILIZATION</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_VFR

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917971">KSPROPERTY_CAMERACONTROL_EXTENDED_VFR</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_FACEDETECTION

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917937">KSPROPERTY_CAMERACONTROL_EXTENDED_FACEDETECTION</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOHDR

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn936752">KSPROPERTY_CAMERACONTROL_EXTENDED_VIDEOHDR</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_HISTOGRAM

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917945">KSPROPERTY_CAMERACONTROL_EXTENDED_HISTOGRAM</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_OIS

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917954">KSPROPERTY_CAMERACONTROL_EXTENDED_OIS</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_ADVANCEDPHOTO

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917934">KSPROPERTY_CAMERACONTROL_EXTENDED_ADVANCEDPHOTO</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE

This enumerates the        <a href="https://msdn.microsoft.com/library/windows/hardware/dn917960">KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE</a> control.


### -field KSPROPERTY_CAMERACONTROL_EXTENDED_END2

This represents the end of the control enumerations.


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