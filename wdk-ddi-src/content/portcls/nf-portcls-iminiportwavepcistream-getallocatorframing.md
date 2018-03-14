---
UID: NF:portcls.IMiniportWavePciStream.GetAllocatorFraming
title: IMiniportWavePciStream::GetAllocatorFraming method
author: windows-driver-content
description: The GetAllocatorFraming method gets the preferred allocator-framing parameters for the stream.
old-location: audio\iminiportwavepcistream_getallocatorframing.htm
old-project: audio
ms.assetid: 0b140ddc-52b5-4aee-afeb-5b2be57fe7b7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetAllocatorFraming method [Audio Devices], GetAllocatorFraming method [Audio Devices], IMiniportWavePciStream interface, GetAllocatorFraming,IMiniportWavePciStream.GetAllocatorFraming, IMiniportWavePciStream, IMiniportWavePciStream interface [Audio Devices], GetAllocatorFraming method, IMiniportWavePciStream::GetAllocatorFraming, audio.iminiportwavepcistream_getallocatorframing, audmp-routines_aef1d53f-2db6-4372-90fa-fb501c199e41.xml, portcls/IMiniportWavePciStream::GetAllocatorFraming
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWavePciStream.GetAllocatorFraming
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# GetAllocatorFraming method
The <code>GetAllocatorFraming</code> method gets the preferred allocator-framing parameters for the stream.

## Syntax

````
NTSTATUS GetAllocatorFraming(
  [out] PKSALLOCATOR_FRAMING AllocatorFraming
);
````

## Parameters

`AllocatorFraming`

Pointer to a <a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a> structure into which the method writes the miniport driver's allocator-framing preferences for this stream.


## Return Value

<code>GetAllocatorFraming</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The miniport driver should not assume that the actual allocator-framing parameters for the stream match those specified in the <code>GetAllocatorFraming</code> call. The port driver interprets the allocation-framing parameters from the <code>GetAllocatorFraming</code> as the miniport driver's preferences. Other factors might outweigh these preferences, however, when the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">SysAudio system driver</a> builds the audio filter graph.

See the discussion of allocator framing in <a href="https://msdn.microsoft.com/6d83c015-cf8f-40b4-bf28-de865a5bfe2d">WavePci Latency</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>



<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePciStream::GetAllocatorFraming method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>