---
UID: NS.KSMEDIA.PKSWAVE_VOLUME
title: PKSWAVE_VOLUME
author: windows-driver-content
description: The KSWAVE_VOLUME structure is used to describe sample volume.
old-location: stream\kswave_volume.htm
old-project: stream
ms.assetid: bf3a0b49-ecec-4e96-bf09-b269e8852422
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSWAVE_VOLUME, *PKSWAVE_VOLUME, KSWAVE_VOLUME
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
req.alt-api: KSWAVE_VOLUME
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

# PKSWAVE_VOLUME structure



## -description
The KSWAVE_VOLUME structure is used to describe sample volume.


## -syntax

````
typedef struct {
  LONG LeftAttenuation;
  LONG RightAttenuation;
} KSWAVE_VOLUME, *PKSWAVE_VOLUME;
````


## -struct-fields

### -field LeftAttenuation

Specifies the amount of left attenuation.

### -field RightAttenuation

Specifies the amount of right attenuation.

## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566529">KSPROPERTY_WAVE_VOLUME</a> property.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566529">KSPROPERTY_WAVE_VOLUME</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_VOLUME structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
