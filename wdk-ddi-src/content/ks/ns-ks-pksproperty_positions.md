---
UID: NS.KS.PKSPROPERTY_POSITIONS
title: PKSPROPERTY_POSITIONS
author: windows-driver-content
description: The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.
old-location: stream\ksproperty_positions.htm
old-project: stream
ms.assetid: 869d3a3f-e2f8-4c23-864b-d40f3e67a9ec
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_POSITIONS
req.alt-loc: ks.h
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

# PKSPROPERTY_POSITIONS structure



## -description
The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.


## -syntax

````
typedef struct {
  LONGLONG         Current;
  LONGLONG         Stop;
  KS_SEEKING_FLAGS CurrentFlags;
  KS_SEEKING_FLAGS StopFlags;
} KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS;
````


## -struct-fields

### -field Current

Specifies the current position as a 64-bit value.

### -field Stop

Specifies the stop position as a 64-bit value.

### -field CurrentFlags

A structure of type <a href="..\ks\ne-ks-ks_seeking_flags.md">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Current</b> parameter.

### -field StopFlags

A structure of type <a href="..\ks\ne-ks-ks_seeking_flags.md">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Stop</b> parameter.

## -remarks
The KSPROPERTY_POSITIONS structure is used with positioning properties in the KSPROPSETID_MediaSeeking property set. These properties correspond to DirectShow's <b>IMediaSeeking::GetPositions</b> and <b>IMediaSeeking::SetPositions</b>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565185">KSPROPERTY_MEDIASEEKING_POSITIONS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_POSITIONS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
