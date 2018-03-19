---
UID: NS:ksmedia.KSDS3D_LISTENER_ALL
title: KSDS3D_LISTENER_ALL
author: windows-driver-content
description: The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ALL property.
old-location: audio\ksds3d_listener_all.htm
old-project: audio
ms.assetid: 6bff18d1-77bf-49c0-af9c-aa1abbfbfa53
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSDS3D_LISTENER_ALL, KSDS3D_LISTENER_ALL, KSDS3D_LISTENER_ALL structure [Audio Devices], PKSDS3D_LISTENER_ALL, PKSDS3D_LISTENER_ALL structure pointer [Audio Devices], aud-prop_1fd24ba2-9b2d-4ee2-b40c-eb7812597da0.xml, audio.ksds3d_listener_all, ksmedia/KSDS3D_LISTENER_ALL, ksmedia/PKSDS3D_LISTENER_ALL"
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
-	KSDS3D_LISTENER_ALL
product: Windows
targetos: Windows
req.typenames: KSDS3D_LISTENER_ALL, *PKSDS3D_LISTENER_ALL
---

# KSDS3D_LISTENER_ALL structure
The KSDS3D_LISTENER_ALL structure specifies all the properties of the DirectSound 3D listener. This structure is used to get or set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537334">KSPROPERTY_DIRECTSOUND3DLISTENER_ALL</a> property.

## Syntax
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

## Members


`Position`

Specifies the position vector of the 3D listener. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>.

`Velocity`

Specifies the velocity vector of the 3D listener. This member is a structure of type DS3DVECTOR.

`OrientFront`

Specifies the front orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.

`OrientTop`

Specifies the top orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.

`DistanceFactor`

Specifies the distance factor for the 3D listener.

`RolloffFactor`

Specifies the rolloff factor for the 3D listener.

`DopplerFactor`

Specifies the Doppler factor for the 3D listener.

## Remarks
This structure is similar to the DS3DBUFFER structure that is described in the Microsoft Windows SDK documentation. The Windows SDK documentation also discusses the distance, rolloff, and Doppler factors for DirectSound 3D listeners.

DirectSound uses this property to implement the <b>IDirectSound3DListener::GetAllParameters</b> and <b>IDirectSound3DListener::SetAllParameters</b> methods, which are described in the Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537334">KSPROPERTY_DIRECTSOUND3DLISTENER_ALL</a>