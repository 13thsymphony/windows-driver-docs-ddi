---
UID: NF:portcls.IMiniportWaveRTOutputStream.GetPacketCount
title: IMiniportWaveRTOutputStream::GetPacketCount method
author: windows-driver-content
description: GetPacketCount returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware.
old-location: audio\iminiportwavertoutputstream_getpacketcount.htm
old-project: audio
ms.assetid: F2870421-2A6F-4E63-AC91-E251E0B67C06
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetPacketCount method [Audio Devices], GetPacketCount method [Audio Devices], IMiniportWaveRTOutputStream interface, GetPacketCount,IMiniportWaveRTOutputStream.GetPacketCount, IMiniportWaveRTOutputStream, IMiniportWaveRTOutputStream interface [Audio Devices], GetPacketCount method, IMiniportWaveRTOutputStream::GetPacketCount, audio.iminiportwavertoutputstream_getpacketcount, portcls/IMiniportWaveRTOutputStream::GetPacketCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
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
req.irql: Passive level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRTOutputStream.GetPacketCount
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# GetPacketCount method
GetPacketCount returns the (1-based) count of packets completely transferred from the WaveRT buffer into hardware.

## Syntax

````
NTSTATUS GetPacketCount(
  [out] UINT64 *pPacketCount 
);
````

## Parameters

`pPacketCount`

pPacketCount returns the number of packets completely transferred from the WaveRT buffer into hardware.


## Return Value

<code>GetPacketCount</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.

## Remarks

From the packet count, the OS can derive the stream position of the packets it writes into the WaveRT buffer. The OS can also derive the WaveRT buffer position of the next packet to write within the WaveRT buffer. For WaveRT drivers, the driver signals a single notification event as it transfers data from each packet of the WaveRT buffer. Therefore the event alone cannot indicate which packet within the WaveRT buffer is being transferred. In normal operation this is not a concern but in underflow cases correction is more easily achieved by querying the packet count from which the OS can determine which packet to write next.

The returned PacketCount indicates the (1-based) count of packets completely transferred from the WaveRT buffer into hardware. From this, the OS can determine the 0-based number of the packet currently being transferred, and ensure that it writes ahead of that packet. For example, if the packet count is 5, then 5 packets have completely transferred. That is, packets 0-4 have completely transferred. Therefore packet 5 is in progress, and the OS should write packet 6. If the notification count for the WaveRT buffer is 2, then packet 6 would be at offset 0 within the WaveRT buffer (because 6 modulo 2 is 0, and 0 times the packet size is 0). 


The OS may get this property at any time. However it generally gets this property only periodically or after the driver returns a dataflow error (STATUS_DATA_LATE_ERROR, STATUS_DATA_OVERRUN) from SetWritePacket() in order to resynchronize with the driver. 


The driver should reset the packet count to 0 when the stream is in KSSTATE_STOP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10 and later.  |
| **Target Platform** | Windows |
| **Header** | portcls.h |
| **IRQL** | Passive level |

## See Also

<a href="..\portcls\nn-portcls-iminiportwavertoutputstream.md">IMiniportWaveRTOutputStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTOutputStream::GetPacketCount method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>