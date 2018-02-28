---
UID: NS:ksmedia._timecode
title: "_timecode"
author: windows-driver-content
description: The TIMECODE union describes a timecode from an external device. This structure is no longer used.
old-location: stream\timecode.htm
old-project: stream
ms.assetid: 3387e014-3a62-4d76-ac6d-6446e4fa39d0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PTIMECODE, PTIMECODE, PTIMECODE union pointer [Streaming Media Devices], TIMECODE, TIMECODE union [Streaming Media Devices], _timecode, ksmedia/PTIMECODE, ksmedia/TIMECODE, stream.timecode, vidcapstruct_80e1d01b-8140-49e8-83bd-210fb38ea0bc.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	TIMECODE
product: Windows
targetos: Windows
req.typenames: TIMECODE
---

# _timecode structure
The TIMECODE union describes a timecode from an external device. This structure is no longer used.

## Syntax
````
typedef union _timecode {
  struct {
    WORD  wFrameRate;
    WORD  wFrameFract;
    DWORD dwFrames;
  };
  DWORDLONG qw;
} TIMECODE, *PTIMECODE;
````

## Members


`qw`

Specifies the timecode as a quad-word.

## Remarks
This structure is defined for the purpose of searching to a timecode based on an absolute track number (ATN) and/or relative time counter (RTC). However, not all devices support searching to a timecode using this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/f3ff3815-0f4f-4fcb-89bd-e77d8002813c">KSPROPERTY_EXTXPORT_RAW_AVC_CMD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20TIMECODE union%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>