---
UID : NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET
title : tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET
author : windows-driver-content
description : The KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure contains the parameters for the Camera Angle Offset Control property.
old-location : stream\kscamera_extendedprop_cameraoffset.htm
old-project : stream
ms.assetid : D6C03D60-9FC4-4EF1-A7DD-4A91990D5CF1
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, *PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, KSCAMERA_EXTENDEDPROP_CAMERAOFFSET
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.1.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSCAMERA_EXTENDEDPROP_CAMERAOFFSET
req.alt-loc : Ksmedia.h
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
req.typenames : "*PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, KSCAMERA_EXTENDEDPROP_CAMERAOFFSET"
---

# tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure
The <b>KSCAMERA_EXTENDEDPROP_CAMERAOFFSET</b> structure contains the parameters for the <i>Camera Angle Offset Control</i> property. The members contain read-only values for the pitch and yaw angle of the camera position.  The pitch/yaw angle is defined to be an offset from horizontal and vertical axis.

## Syntax
````
typedef struct _KSCAMERA_EXTENDEDPROP_CAMERAOFFSET {
  LONG  PitchAngle;
  LONG  YawAngle;
  ULONG Flag;
  ULONG Reserved;
} KSCAMERA_EXTENDEDPROP_CAMERAOFFSET, *PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET;
````

## Members

        
            `Flag`

            Reserved. Set to 0.
        
            `PitchAngle`

            The angle offset of the camera look direction from the horizontal axis of the camera facing direction.
        
            `Reserved`

            Reserved. Set to 0.
        
            `YawAngle`

            The angle offset of the camera look direction from the vertical axis of the camera facing direction.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_header.md">KSCAMERA_EXTENDEDPROP_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567571">KSPROPERTY_CAMERACONTROL_EXTENDED_CAMERAANGLEOFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>