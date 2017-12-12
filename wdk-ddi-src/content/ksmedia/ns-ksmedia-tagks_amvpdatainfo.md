---
UID: NS.KSMEDIA.TAGKS_AMVPDATAINFO
title: tagKS_AMVPDATAINFO
author: windows-driver-content
description: The KS_AMVPDATAINFO structure is used to describe the properties of a video port.
old-location: stream\ks_amvpdatainfo.htm
old-project: stream
ms.assetid: 4c217cf8-ca93-4e5d-8cbc-c56794f96d50
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: tagKS_AMVPDATAINFO, KS_AMVPDATAINFO, *PKS_AMVPDATAINFO
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
req.alt-api: KS_AMVPDATAINFO
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

# tagKS_AMVPDATAINFO structure



## -description
The KS_AMVPDATAINFO structure is used to describe the properties of a video port.



## -syntax

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


## -struct-fields

### -field dwSize

Specifies the size of the structure, in bytes.


### -field dwMicrosecondsPerField

Specifies the time taken by each field, in microseconds (millionths of a second).


### -field amvpDimInfo

Describes the dimensional information of the video port, such as field and VBI dimensions.


### -field dwPictAspectRatioX

Indicates the picture aspect ratio in the horizontal dimension. For example, for a 16x9 aspect ratio this member would be 16.


### -field dwPictAspectRatioY

Indicates the picture aspect ratio in the vertical dimension. For example, for a 4x3 aspect ratio this member would be 3.


### -field bEnableDoubleClock

Specifies if the video port should enable double clocking. 


### -field bEnableVACT

Specifies if the video port should use an external VACT signal.


### -field bDataIsInterlaced

Indicates that the signal is interlaced.


### -field lHalfLinesOdd

Indicates the number of halflines in the odd field.


### -field bFieldPolarityInverted

Indicates if the device inverts the field polarity by default.


### -field dwNumLinesInVREF

Specifies the number of lines of data in VREF.


### -field lHalfLinesEven

Indicates the number of halflines in the even field.


### -field dwReserved1

Reserved for future use. Do not use.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a> property.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPDATAINFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

