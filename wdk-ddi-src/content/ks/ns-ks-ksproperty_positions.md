---
UID: NS:ks.KSPROPERTY_POSITIONS
title: KSPROPERTY_POSITIONS
author: windows-driver-content
description: The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.
old-location: stream\ksproperty_positions.htm
old-project: stream
ms.assetid: 869d3a3f-e2f8-4c23-864b-d40f3e67a9ec
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS structure [Streaming Media Devices], PKSPROPERTY_POSITIONS, PKSPROPERTY_POSITIONS structure pointer [Streaming Media Devices], ks-struct_97829290-4c01-4a03-b56b-3e5915941094.xml, ks/KSPROPERTY_POSITIONS, ks/PKSPROPERTY_POSITIONS, stream.ksproperty_positions"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPROPERTY_POSITIONS
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS
---

# KSPROPERTY_POSITIONS structure
The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.

## Syntax
````
typedef struct {
  LONGLONG         Current;
  LONGLONG         Stop;
  KS_SEEKING_FLAGS CurrentFlags;
  KS_SEEKING_FLAGS StopFlags;
} KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS;
````

## Members


`Current`

Specifies the current position as a 64-bit value.

`CurrentFlags`

A structure of type <a href="..\ks\ne-ks-ks_seeking_flags.md">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Current</b> parameter.

`Stop`

Specifies the stop position as a 64-bit value.

`StopFlags`

A structure of type <a href="..\ks\ne-ks-ks_seeking_flags.md">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Stop</b> parameter.

## Remarks
The KSPROPERTY_POSITIONS structure is used with positioning properties in the KSPROPSETID_MediaSeeking property set. These properties correspond to DirectShow's <b>IMediaSeeking::GetPositions</b> and <b>IMediaSeeking::SetPositions</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565185">KSPROPERTY_MEDIASEEKING_POSITIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_POSITIONS structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>