---
UID: NS.KSMEDIA.PKSDS3D_LISTENER_ALL
title: PKSDS3D_LISTENER_ALL
author: windows-driver-content
description: The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ALL property.
old-location: audio\ksds3d_listener_all.htm
old-project: audio
ms.assetid: 6bff18d1-77bf-49c0-af9c-aa1abbfbfa53
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSDS3D_LISTENER_ALL, KSDS3D_LISTENER_ALL, *PKSDS3D_LISTENER_ALL
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
req.alt-api: KSDS3D_LISTENER_ALL
req.alt-loc: ksmedia.h
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

# PKSDS3D_LISTENER_ALL structure



## -description
The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537334">KSPROPERTY_DIRECTSOUND3DLISTENER_ALL</a> property.



## -syntax

````
typedef struct {
  DS3DVECTOR Position;
  DS3DVECTOR Velocity;
  DS3DVECTOR OrientFront;
  DS3DVECTOR OrientTop;
  FLOAT      DistanceFactor;
  FLOAT      RolloffFactor;
  FLOAT      DopplerFactor;
} KSDS3D_LISTENER_ALL, *PKSDS3D_LISTENER_ALL;
````


## -struct-fields

### -field Position

Specifies the position vector of the 3D listener. This member is a structure of type <a href="audio.ds3dvector">DS3DVECTOR</a>.


### -field Velocity

Specifies the velocity vector of the 3D listener. This member is a structure of type DS3DVECTOR.


### -field OrientFront

Specifies the front orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.


### -field OrientTop

Specifies the top orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.


### -field DistanceFactor

Specifies the distance factor for the 3D listener.


### -field RolloffFactor

Specifies the rolloff factor for the 3D listener.


### -field DopplerFactor

Specifies the Doppler factor for the 3D listener.


## -remarks
This structure is similar to the DS3DBUFFER structure that is described in the Microsoft Windows SDK documentation. The Windows SDK documentation also discusses the distance, rolloff, and Doppler factors for DirectSound 3D listeners.

DirectSound uses this property to implement the <b>IDirectSound3DListener::GetAllParameters</b> and <b>IDirectSound3DListener::SetAllParameters</b> methods, which are described in the Windows SDK documentation.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.ds3dvector">DS3DVECTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537334">KSPROPERTY_DIRECTSOUND3DLISTENER_ALL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_LISTENER_ALL structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

