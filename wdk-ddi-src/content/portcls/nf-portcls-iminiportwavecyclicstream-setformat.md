---
UID: NF:portcls.IMiniportWaveCyclicStream.SetFormat
title: IMiniportWaveCyclicStream::SetFormat method
author: windows-driver-content
description: The SetFormat method sets the KS data format of the wave stream.
old-location: audio\iminiportwavecyclicstream_setformat.htm
old-project: audio
ms.assetid: 6881ea55-138a-408e-955e-c5c74f777ce8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportWaveCyclicStream, IMiniportWaveCyclicStream::SetFormat, audio.iminiportwavecyclicstream_setformat, IMiniportWaveCyclicStream interface [Audio Devices], SetFormat method, SetFormat method [Audio Devices], SetFormat, audmp-routines_d23a09d4-7110-425f-b10d-5f7f601179bb.xml, portcls/IMiniportWaveCyclicStream::SetFormat, SetFormat method [Audio Devices], IMiniportWaveCyclicStream interface
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportWaveCyclicStream.SetFormat
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# SetFormat method
The <code>SetFormat</code> method sets the KS data format of the wave stream.

## Syntax

````
NTSTATUS SetFormat(
  [in] PKSDATAFORMAT DataFormat
);
````

## Parameters

`DataFormat`

Specifies the new format of the stream. This parameter is a pointer to a structure of type <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>.


## Return Value

<code>SetFormat</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The wave stream's initial format is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a> call that creates the stream. Following stream creation, the <code>SetFormat</code> call can change the stream's format from its initial setting.

For information about specifying wave stream formats, see <a href="https://msdn.microsoft.com/85aa74b4-8e33-49f4-82e7-561baa55c265">Audio Data Formats and Data Ranges</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

<a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveCyclicStream::SetFormat method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>