---
UID: NS:ksmedia.KSWAVE_INPUT_CAPABILITIES
title: KSWAVE_INPUT_CAPABILITIES
author: windows-driver-content
description: The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.
old-location: stream\kswave_input_capabilities.htm
old-project: stream
ms.assetid: 8bed3cec-1779-4b3c-9ba2-aa4a335fecd1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.kswave_input_capabilities, *PKSWAVE_INPUT_CAPABILITIES, ksmedia/PKSWAVE_INPUT_CAPABILITIES, KSWAVE_INPUT_CAPABILITIES, ksmedia/KSWAVE_INPUT_CAPABILITIES, dvdref_cc35df03-82e2-4b12-a08f-26aa0fde1279.xml, PKSWAVE_INPUT_CAPABILITIES, PKSWAVE_INPUT_CAPABILITIES structure pointer [Streaming Media Devices], KSWAVE_INPUT_CAPABILITIES structure [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSWAVE_INPUT_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: KSWAVE_INPUT_CAPABILITIES, *PKSWAVE_INPUT_CAPABILITIES
---

# KSWAVE_INPUT_CAPABILITIES structure
The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.

## Syntax
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

## Members


`ActiveConnections`

Indicates the number of active connections.

`MaximumBitsPerSample`

Specifies the maximum bits per sample.

`MaximumChannelsPerConnection`

Specifies the maximum channels per connection.

`MaximumSampleFrequency`

Specifies the maximum sampling frequency.

`MinimumBitsPerSample`

Specifies the minimum bits per sample.

`MinimumSampleFrequency`

Specifies the minimum sampling frequency.

`TotalConnections`

Indicates the total number of connections.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566521">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566521">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_INPUT_CAPABILITIES structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>