---
UID : NS:ksmedia.KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
title : KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
author : windows-driver-content
description : The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device.
old-location : stream\ksproperty_videocompression_getinfo_s.htm
old-project : stream
ms.assetid : a34f051e-9769-427e-b1a7-2718a023e9d1
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure [Streaming Media Devices], stream.ksproperty_videocompression_getinfo_s, *PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, vidcapstruct_28f47a4f-d28e-40b4-acc5-42835ec89b40.xml, ksmedia/PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
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
req.typenames : KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, *PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
---

# KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure
The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  ULONG      StreamIndex;
  LONG       DefaultKeyFrameRate;
  LONG       DefaultPFrameRate;
  LONG       DefaultQuality;
  LONG       NumberOfQualitySettings;
  LONG       Capabilities;
} KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, *PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S;
````

## Members


`Capabilities`

Specifies the compression capabilities of the device. This member can be one or more (logically ORed) of the values from the <a href="..\ksmedia\ne-ksmedia-ks_compressioncaps.md">KS_CompressionCaps</a> enumeration.

`DefaultKeyFrameRate`

Indicates the estimated number of frames per key frame.

`DefaultPFrameRate`

Indicates the predicted number of frames per key frame.

`DefaultQuality`

Specifies the default quality value. This value should be in the range from 0 through 10000.

`NumberOfQualitySettings`

Indicates the number of discrete compression quality settings the device supports.

`Property`

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

`StreamIndex`

Specifies the zero-based index of the stream being queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567813">PROPSETID_VIDCAP_VIDEOCOMPRESSION</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ne-ksmedia-ks_compressioncaps.md">KS_CompressionCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>