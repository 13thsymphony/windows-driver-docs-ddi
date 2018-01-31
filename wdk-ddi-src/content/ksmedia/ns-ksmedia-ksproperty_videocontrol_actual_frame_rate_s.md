---
UID : NS:ksmedia.KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
title : KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
author : windows-driver-content
description : The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests.
old-location : stream\ksproperty_videocontrol_actual_frame_rate_s.htm
old-project : stream
ms.assetid : 98b6c085-d7d0-47e4-acea-a272487f20c2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksmedia/KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, stream.ksproperty_videocontrol_actual_frame_rate_s, *PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, vidcapstruct_7ae44134-3ba1-4419-9290-c305f345e29c.xml, KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure pointer [Streaming Media Devices], KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, *PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
---

# KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure
The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  ULONG      StreamIndex;
  ULONG      RangeIndex;
  SIZE       Dimensions;
  LONGLONG   CurrentActualFrameRate;
  LONGLONG   CurrentMaxAvailableFrameRate;
} KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, *PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S;
````

## Members


`CurrentActualFrameRate`

Specifies the actual frame rate for the specified stream and range. Frame rate values are expressed in 100-nanosecond units.

`CurrentMaxAvailableFrameRate`

Specifies the maximum frame rate for the specified stream and range. Frame rate values are expressed in 100-nanosecond units.

`Dimensions`

Specifies the width and height of the image.

`Property`

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

`RangeIndex`

Contains the zero-based index into the range list. The value contained at this location specifies the range in which frame rate information is being requested.

`StreamIndex`

Contains the zero-based index of the stream.

## Remarks
The minidriver should return STATUS_NOT_SUPPORTED if the pin is not open.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566024">KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>