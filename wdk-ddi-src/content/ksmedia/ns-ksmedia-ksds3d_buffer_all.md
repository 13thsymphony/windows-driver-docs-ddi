---
UID: NS:ksmedia.KSDS3D_BUFFER_ALL
title: KSDS3D_BUFFER_ALL
author: windows-driver-content
description: The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.
old-location: audio\ksds3d_buffer_all.htm
old-project: audio
ms.assetid: c94e2189-62a6-44d6-9a29-4fd32c72437a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSDS3D_BUFFER_ALL, KSDS3D_BUFFER_ALL, KSDS3D_BUFFER_ALL structure [Audio Devices], PKSDS3D_BUFFER_ALL, PKSDS3D_BUFFER_ALL structure pointer [Audio Devices], aud-prop_46bd2b81-3d2a-49e1-93e6-867e84ae4c04.xml, audio.ksds3d_buffer_all, ksmedia/KSDS3D_BUFFER_ALL, ksmedia/PKSDS3D_BUFFER_ALL"
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
-	KSDS3D_BUFFER_ALL
product: Windows
targetos: Windows
req.typenames: KSDS3D_BUFFER_ALL, *PKSDS3D_BUFFER_ALL
---

# KSDS3D_BUFFER_ALL structure
The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.

## Syntax
````
typedef struct {
  DS3DVECTOR Position;
  DS3DVECTOR Velocity;
  ULONG      InsideConeAngle;
  ULONG      OutsideConeAngle;
  DS3DVECTOR ConeOrientation;
  LONG       ConeOutsideVolume;
  FLOAT      MinDistance;
  FLOAT      MaxDistance;
  ULONG      Mode;
} KSDS3D_BUFFER_ALL, *PKSDS3D_BUFFER_ALL;
````

## Members


`Position`

Specifies the x, y, and z position coordinates of the 3D sound buffer. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>.

`Velocity`

Specifies the x, y, and z velocity components of the 3D sound buffer. This member is a structure of type DS3DVECTOR.

`InsideConeAngle`

Specifies the angle in degrees of the inside sound projection cone.

`OutsideConeAngle`

Specifies the angle in degrees of the outside sound projection cone.

`ConeOrientation`

Specifies the x, y, and z components of the orientation of the 3D buffer's sound projection cone. This member is a structure of type DS3DVECTOR.

`ConeOutsideVolume`

Specifies the cone outside volume.

`MinDistance`

Specifies the minimum distance between the speaker and listener. (See the discussion of minimum and maximum distances for DirectSound 3D buffers in the Microsoft Windows SDK documentation.)

`MaxDistance`

Specifies the maximum distance between the speaker and listener.

`Mode`

Specifies the 3D sound-processing mode. This can be one of the following values from the header file Dsound.h:

<ul>
<li>
DS3DMODE_DISABLE 

</li>
<li>
DS3DMODE_HEADRELATIVE 

</li>
<li>
DS3DMODE_NORMAL

</li>
</ul>
For the meaning of these parameters, see the description of the <b>dwMode</b> member of the DS3DBUFFER structure in the Microsoft Windows SDK documentation.

## Remarks
This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a> property. DirectSound uses this property to implement the <b>IDirectSound3DBuffer::GetAllParameters</b> and <b>IDirectSound3DBuffer::SetAllParameters</b> methods, which are described in the Windows SDK documentation.

The members of this structure are similar to those defined for the DS3DBUFFER structure in the Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a>