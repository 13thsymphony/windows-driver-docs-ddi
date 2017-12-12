---
UID: NS.KSMEDIA.PKSWAVE_INPUT_CAPABILITIES
title: PKSWAVE_INPUT_CAPABILITIES
author: windows-driver-content
description: The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.
old-location: stream\kswave_input_capabilities.htm
old-project: stream
ms.assetid: 8bed3cec-1779-4b3c-9ba2-aa4a335fecd1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSWAVE_INPUT_CAPABILITIES, *PKSWAVE_INPUT_CAPABILITIES, KSWAVE_INPUT_CAPABILITIES
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
req.alt-api: KSWAVE_INPUT_CAPABILITIES
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

# PKSWAVE_INPUT_CAPABILITIES structure



## -description
The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.



## -syntax

````
typedef struct {
  ULONG MaximumChannelsPerConnection;
  ULONG MinimumBitsPerSample;
  ULONG MaximumBitsPerSample;
  ULONG MinimumSampleFrequency;
  ULONG MaximumSampleFrequency;
  ULONG TotalConnections;
  ULONG ActiveConnections;
} KSWAVE_INPUT_CAPABILITIES, *PKSWAVE_INPUT_CAPABILITIES;
````


## -struct-fields

### -field MaximumChannelsPerConnection

Specifies the maximum channels per connection.


### -field MinimumBitsPerSample

Specifies the minimum bits per sample.


### -field MaximumBitsPerSample

Specifies the maximum bits per sample.


### -field MinimumSampleFrequency

Specifies the minimum sampling frequency.


### -field MaximumSampleFrequency

Specifies the maximum sampling frequency.


### -field TotalConnections

Indicates the total number of connections.


### -field ActiveConnections

Indicates the number of active connections.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566521">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a> property.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566521">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_INPUT_CAPABILITIES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

