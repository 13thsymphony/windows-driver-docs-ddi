---
UID: NS:hdaudio._HDAUDIO_CONVERTER_FORMAT
title: "_HDAUDIO_CONVERTER_FORMAT"
author: windows-driver-content
description: The HDAUDIO_CONVERTER_FORMAT structure specifies the 16-bit encoded stream format for an input or output converter, as defined in the Intel High Definition Audio Specification (see the Intel HD Audio website).
old-location: audio\hdaudio_converter_format.htm
old-project: audio
ms.assetid: 623f58f6-db82-4a4a-bac3-cc821babfe99
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PHDAUDIO_CONVERTER_FORMAT, HDAUDIO_CONVERTER_FORMAT, HDAUDIO_CONVERTER_FORMAT structure [Audio Devices], PHDAUDIO_CONVERTER_FORMAT, PHDAUDIO_CONVERTER_FORMAT structure pointer [Audio Devices], _HDAUDIO_CONVERTER_FORMAT, aud-prop2_fbc3cdcb-94a1-43ef-bf23-4b1cca37e99d.xml, audio.hdaudio_converter_format, hdaudio/HDAUDIO_CONVERTER_FORMAT, hdaudio/PHDAUDIO_CONVERTER_FORMAT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hdaudio.h
api_name:
-	HDAUDIO_CONVERTER_FORMAT
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_CONVERTER_FORMAT, *PHDAUDIO_CONVERTER_FORMAT
---

# _HDAUDIO_CONVERTER_FORMAT structure
The HDAUDIO_CONVERTER_FORMAT structure specifies the 16-bit encoded stream format for an input or output converter, as defined in the Intel High Definition Audio Specification (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website).

## Syntax
```
typedef struct _HDAUDIO_CONVERTER_FORMAT {
  union {
    struct {
      USHORT  : 4 NumberOfChannels;
      USHORT  : 3 BitsPerSample;
      USHORT  : 7 SampleRate;
      USHORT  : 1 StreamType;
    };
    USHORT ConverterFormat;
  };
} HDAUDIO_CONVERTER_FORMAT, *PHDAUDIO_CONVERTER_FORMAT;
```

## Members


## Remarks
For information about the encoding of the individual bitfields in the structure definition, see the discussion of the stream descriptor in the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

The HD Audio bus driver sets the unnamed bitfield in the structure definition to zero.

The <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a>, <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>, and <a href="https://msdn.microsoft.com/4dcf8fb6-71f5-4e11-a92a-0292c2a1515c">ChangeBandwidthAllocation</a> routines take as an input parameter an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536430">HDAUDIO_STREAM_FORMAT</a> structure and output the corresponding HDAUDIO_CONVERTER_FORMAT structure. The caller can use the output value to program the input or output converters.

Each valid HDAUDIO_CONVERTER_FORMAT encoding has a one-to-one correspondence to an HDAUDIO_STREAM_FORMAT structure that contains a valid set of parameters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hdaudio.h (include Hdaudio.h) |

## See Also

<a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a>



<a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>



<a href="https://msdn.microsoft.com/4dcf8fb6-71f5-4e11-a92a-0292c2a1515c">ChangeBandwidthAllocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536430">HDAUDIO_STREAM_FORMAT</a>