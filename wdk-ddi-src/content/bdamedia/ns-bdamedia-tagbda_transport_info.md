---
UID: NS:bdamedia.tagBDA_TRANSPORT_INFO
title: tagBDA_TRANSPORT_INFO
author: windows-driver-content
description: The BDA_TRANSPORT_INFO structure describes formatting for a stream connection.
old-location: stream\bda_transport_info.htm
old-project: stream
ms.assetid: 995a1d2f-8e2b-426e-a08c-283124ce905e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: bdamedia/PBDA_TRANSPORT_INFO, PBDA_TRANSPORT_INFO, stream.bda_transport_info, BDA_TRANSPORT_INFO structure [Streaming Media Devices], bdaref_3ee17c26-da8b-4d04-87fc-6c9912de349d.xml, tagBDA_TRANSPORT_INFO, BDA_TRANSPORT_INFO, bdamedia/BDA_TRANSPORT_INFO, *PBDA_TRANSPORT_INFO, PBDA_TRANSPORT_INFO structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
apiname:
-	BDA_TRANSPORT_INFO
product: Windows
targetos: Windows
req.typenames: "*PBDA_TRANSPORT_INFO, BDA_TRANSPORT_INFO"
---

# tagBDA_TRANSPORT_INFO structure
The BDA_TRANSPORT_INFO structure describes formatting for a stream connection.

## Syntax
````
typedef struct tagBDA_TRANSPORT_INFO {
  ULONG          ulcbPhyiscalPacket;
  ULONG          ulcbPhyiscalFrame;
  ULONG          ulcbPhyiscalFrameAlignment;
  REFERENCE_TIME AvgTimePerFrame;
} BDA_TRANSPORT_INFO, *PBDA_TRANSPORT_INFO;
````

## Members


`AvgTimePerFrame`

REFERENCE TIME value that indicates the video frame's average display time, in 100-nanosecond units.

`ulcbPhyiscalFrame`

Size, in bytes, of each physical frame (0 indicates no hardware requirement).

`ulcbPhyiscalFrameAlignment`

Capture buffer alignment in bytes (0 and 1 indicate no alignment requirements).

`ulcbPhyiscalPacket`

Size, in bytes, of a physical packet (for example, the size of a satellite link payload).

## Remarks
A BDA_TRANSPORT_INFO structure in conjunction with a KSDATARANGE structure makes up a KS_DATARANGE_BDA_TRANSPORT data range. A data range describes a range of data formats. 

Pins of filters specify the data ranges they support to enable stream connections to pins of other filters that also support those data ranges.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdamedia.h (include Bdamedia.h) |

## See Also

<a href="..\bdamedia\ns-bdamedia-tagks_datarange_bda_transport.md">KS_DATARANGE_BDA_TRANSPORT</a>



<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_TRANSPORT_INFO structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>