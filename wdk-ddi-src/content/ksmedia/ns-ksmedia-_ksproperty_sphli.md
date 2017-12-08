---
UID: NS.KSMEDIA._KSPROPERTY_SPHLI
title: _KSPROPERTY_SPHLI
author: windows-driver-content
description: The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed.
old-location: stream\ksproperty_sphli.htm
old-project: stream
ms.assetid: e1ee8d13-7f83-4020-9f34-4b2c3626685b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSPROPERTY_SPHLI, *PKSPROPERTY_SPHLI, KSPROPERTY_SPHLI
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
req.alt-api: KSPROPERTY_SPHLI
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

# _KSPROPERTY_SPHLI structure



## -description
The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed.


## -syntax

````
typedef struct _KSPROPERTY_SPHLI {
  USHORT    HLISS;
  USHORT    Reserved;
  ULONG     StartPTM;
  ULONG     EndPTM;
  USHORT    StartX;
  USHORT    StartY;
  USHORT    StopX;
  USHORT    StopY;
  KS_COLCON ColCon;
} KSPROPERTY_SPHLI, *PKSPROPERTY_SPHLI;
````


## -struct-fields

### -field HLISS

Indicates the highlight status of the current selection. A value of zero indicates that all highlights are invalid and the decoder should disable all highlights.

### -field Reserved

Reserved. Do not use.

### -field StartPTM

Indicates the start of presentation time.

### -field EndPTM

Indicates the end of presentation time.

### -field StartX

Indicates the start x-coordinate pixel of the current highlight button.

### -field StartY

Indicates the start y-coordinate pixel of the current highlight button.

### -field StopX

Indicates the ending x-coordinate pixel of the current highlight button.

### -field StopY

Indicates the ending y-coordinate pixel of the current highlight button.

### -field ColCon

Specifies the color/contrast of the highlight rectangle.

## -remarks
The KSPROPERTY_SPHLI structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565150">KSPROPERTY_DVDSUBPIC_HLI</a> property.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565150">KSPROPERTY_DVDSUBPIC_HLI</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SPHLI structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
