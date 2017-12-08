---
UID: NS.KSMEDIA.PKSWAVE_BUFFER
title: PKSWAVE_BUFFER
author: windows-driver-content
description: The KSWAVE_BUFFER structure is used to describe a sample buffer.
old-location: stream\kswave_buffer.htm
old-project: stream
ms.assetid: 1bd19fcd-90da-4e1a-ac9a-692c6fddc7ab
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSWAVE_BUFFER, KSWAVE_BUFFER, *PKSWAVE_BUFFER
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
req.alt-api: KSWAVE_BUFFER
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

# PKSWAVE_BUFFER structure



## -description
The KSWAVE_BUFFER structure is used to describe a sample buffer.


## -syntax

````
typedef struct {
  ULONG Attributes;
  ULONG BufferSize;
  PVOID BufferAddress;
} KSWAVE_BUFFER, *PKSWAVE_BUFFER;
````


## -struct-fields

### -field Attributes

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
 

### -field BufferSize

Specifies the size of the buffer, in bytes.

### -field BufferAddress

Specifies the starting address of the buffer.

## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566514">KSPROPERTY_WAVE_BUFFER</a> property.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566514">KSPROPERTY_WAVE_BUFFER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_BUFFER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
