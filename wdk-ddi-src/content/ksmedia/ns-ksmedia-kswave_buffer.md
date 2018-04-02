---
UID: NS:ksmedia.KSWAVE_BUFFER
title: KSWAVE_BUFFER
author: windows-driver-content
description: The KSWAVE_BUFFER structure is used to describe a sample buffer.
old-location: stream\kswave_buffer.htm
old-project: stream
ms.assetid: 1bd19fcd-90da-4e1a-ac9a-692c6fddc7ab
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSWAVE_BUFFER, KSWAVE_BUFFER, KSWAVE_BUFFER structure [Streaming Media Devices], PKSWAVE_BUFFER, PKSWAVE_BUFFER structure pointer [Streaming Media Devices], dvdref_8b774201-3725-497e-8545-10c5cad2ef1f.xml, ksmedia/KSWAVE_BUFFER, ksmedia/PKSWAVE_BUFFER, stream.kswave_buffer"
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
-	KSWAVE_BUFFER
product: Windows
targetos: Windows
req.typenames: KSWAVE_BUFFER, *PKSWAVE_BUFFER
---

# KSWAVE_BUFFER structure
The KSWAVE_BUFFER structure is used to describe a sample buffer.

## Syntax
```
typedef struct KSWAVE_BUFFER {
  ULONG Attributes;
  ULONG BufferSize;
  PVOID BufferAddress;
}  *PKSWAVE_BUFFER;
```

## Members


`Attributes`

Specifies the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSWAVE_BUFFER_ATTRIBUTEF_LOOPING

</td>
<td>
Indicates that the buffer loops.

</td>
</tr>
<tr>
<td>
KSWAVE_BUFFER_ATTRIBUTEF_STATIC

</td>
<td>
Indicates that the buffer is static.

</td>
</tr>
</table>

`BufferSize`

Specifies the size of the buffer, in bytes.

`BufferAddress`

Specifies the starting address of the buffer.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566514">KSPROPERTY_WAVE_BUFFER</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566514">KSPROPERTY_WAVE_BUFFER</a>