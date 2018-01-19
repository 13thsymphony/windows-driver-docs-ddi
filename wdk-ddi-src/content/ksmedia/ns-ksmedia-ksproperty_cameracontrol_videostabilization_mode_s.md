---
UID : NS:ksmedia.KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
title : KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
author : windows-driver-content
description : Describes video stabilization control properties in the PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION camera control property set. This structure specifies property values that are used in requests to the camera driver.
old-location : stream\ksproperty_cameracontrol_videostabilization_mode_s.htm
old-project : stream
ms.assetid : 7cbf015c-4756-4d5c-a5fb-9cd8a5e0e3fd
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
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
req.typenames : "*PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S"
---

# KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure
Describes video stabilization control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION</b> camera control property set. This structure specifies property values that are used in requests to the camera driver.

## Syntax
````
typedef struct {
  ULONG VideoStabilizationMode;
  ULONG Capabilities;
} KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S;
````

## Members

        
            `Capabilities`

            Indicates whether the device and driver support setting video stabilization control automatically or manually. This member a bitwise <b>OR</b> of these possible values:
        
            `VideoStabilizationMode`

            Indicates the selected video stabilization modes. This member has one of these possible values:

    ## Remarks
        The video stabilization settings specified with this structure affect only the device and have no effect on applications' software video stabilization.

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
<a href="..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_video_stabilization_mode.md">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj156043">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>