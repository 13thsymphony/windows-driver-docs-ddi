---
UID: NS:ksmedia.KSDS3D_LISTENER_ORIENTATION
title: KSDS3D_LISTENER_ORIENTATION
author: windows-driver-content
description: A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION property.
old-location: audio\ksds3d_listener_orientation.htm
old-project: audio
ms.assetid: 3bcb9a6f-aacc-4b42-ba8e-1a1a4898f96d
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ksmedia/PKSDS3D_LISTENER_ORIENTATION, PKSDS3D_LISTENER_ORIENTATION structure pointer [Audio Devices], aud-prop_9e525f5b-c264-46e5-84f3-3a7845b61200.xml, ksmedia/KSDS3D_LISTENER_ORIENTATION, KSDS3D_LISTENER_ORIENTATION, audio.ksds3d_listener_orientation, KSDS3D_LISTENER_ORIENTATION structure [Audio Devices], *PKSDS3D_LISTENER_ORIENTATION, PKSDS3D_LISTENER_ORIENTATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSDS3D_LISTENER_ORIENTATION
product: Windows
targetos: Windows
req.typenames: "*PKSDS3D_LISTENER_ORIENTATION, KSDS3D_LISTENER_ORIENTATION"
---

# KSDS3D_LISTENER_ORIENTATION structure
A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537343">KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION</a> property.

## Syntax
````
typedef struct {
  DS3DVECTOR Front;
  DS3DVECTOR Top;
} KSDS3D_LISTENER_ORIENTATION, *PKSDS3D_LISTENER_ORIENTATION;
````

## Members


`Front`

Specifies the front orientation vector of the 3D listener. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>.

`Top`

Specifies the top orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.

## Remarks
DirectSound uses this property to implement the <b>IDirectSound3DListener::GetOrientation</b> and <b>IDirectSound3DListener::SetOrientation</b> methods, which are described in the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537343">KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION</a>



<a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_LISTENER_ORIENTATION structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>