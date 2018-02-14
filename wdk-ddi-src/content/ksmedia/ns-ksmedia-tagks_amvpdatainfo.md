---
UID: NS:ksmedia.tagKS_AMVPDATAINFO
title: tagKS_AMVPDATAINFO
author: windows-driver-content
description: The KS_AMVPDATAINFO structure is used to describe the properties of a video port.
old-location: stream\ks_amvpdatainfo.htm
old-project: stream
ms.assetid: 4c217cf8-ca93-4e5d-8cbc-c56794f96d50
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KS_AMVPDATAINFO, stream.ks_amvpdatainfo, dvdref_e3126cb7-47dc-469b-b2ef-caefc04966cc.xml, KS_AMVPDATAINFO, PKS_AMVPDATAINFO structure pointer [Streaming Media Devices], KS_AMVPDATAINFO structure [Streaming Media Devices], PKS_AMVPDATAINFO, tagKS_AMVPDATAINFO, ksmedia/PKS_AMVPDATAINFO, *PKS_AMVPDATAINFO
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
-	KS_AMVPDATAINFO
product: Windows
targetos: Windows
req.typenames: KS_AMVPDATAINFO, *PKS_AMVPDATAINFO
---

# tagKS_AMVPDATAINFO structure
The KS_AMVPDATAINFO structure is used to describe the properties of a video port.

## Syntax
````
typedef struct tagKS_AMVPDATAINFO {
  DWORD          dwSize;
  DWORD          dwMicrosecondsPerField;
  KS_AMVPDIMINFO amvpDimInfo;
  DWORD          dwPictAspectRatioX;
  DWORD          dwPictAspectRatioY;
  BOOL           bEnableDoubleClock;
  BOOL           bEnableVACT;
  BOOL           bDataIsInterlaced;
  LONG           lHalfLinesOdd;
  BOOL           bFieldPolarityInverted;
  DWORD          dwNumLinesInVREF;
  LONG           lHalfLinesEven;
  DWORD          dwReserved1;
} KS_AMVPDATAINFO, *PKS_AMVPDATAINFO;
````

## Members


`amvpDimInfo`

Describes the dimensional information of the video port, such as field and VBI dimensions.

`bDataIsInterlaced`

Indicates that the signal is interlaced.

`bEnableDoubleClock`

Specifies if the video port should enable double clocking.

`bEnableVACT`

Specifies if the video port should use an external VACT signal.

`bFieldPolarityInverted`

Indicates if the device inverts the field polarity by default.

`dwMicrosecondsPerField`

Specifies the time taken by each field, in microseconds (millionths of a second).

`dwNumLinesInVREF`

Specifies the number of lines of data in VREF.

`dwPictAspectRatioX`

Indicates the picture aspect ratio in the horizontal dimension. For example, for a 16x9 aspect ratio this member would be 16.

`dwPictAspectRatioY`

Indicates the picture aspect ratio in the vertical dimension. For example, for a 4x3 aspect ratio this member would be 3.

`dwReserved1`

Reserved for future use. Do not use.

`dwSize`

Specifies the size of the structure, in bytes.

`lHalfLinesEven`

Indicates the number of halflines in the even field.

`lHalfLinesOdd`

Indicates the number of halflines in the odd field.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPDATAINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>