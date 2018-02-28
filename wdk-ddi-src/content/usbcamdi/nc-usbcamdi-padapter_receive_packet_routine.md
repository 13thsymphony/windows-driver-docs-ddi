---
UID: NC:usbcamdi.PADAPTER_RECEIVE_PACKET_ROUTINE
title: PADAPTER_RECEIVE_PACKET_ROUTINE
author: windows-driver-content
description: A camera minidriver's AdapterReceivePacket callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver.
old-location: stream\adapterreceivepacket.htm
old-project: stream
ms.assetid: 8ee658bf-2243-4b1f-b4d6-5d9b6388e972
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AdapterReceivePacket, AdapterReceivePacket callback function [Streaming Media Devices], PADAPTER_RECEIVE_PACKET_ROUTINE, stream.adapterreceivepacket, usbcamdi/AdapterReceivePacket, usbcmdpr_4f4422ba-64f3-4eee-8450-4a3b5715b910.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	AdapterReceivePacket
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PADAPTER_RECEIVE_PACKET_ROUTINE callback function
A camera minidriver's <i>AdapterReceivePacket</i> callback function processes adapter-based stream request blocks (SRBs) passed to it by the stream class driver.

## Syntax

```
PADAPTER_RECEIVE_PACKET_ROUTINE PadapterReceivePacketRoutine;

void PadapterReceivePacketRoutine(
  PHW_STREAM_REQUEST_BLOCK Srb
)
{...}
```

## Parameters

`Srb`

Specifies the SRB to be processed by the camera minidriver.


## Return Value

<i>AdapterReceivePacket</i> does not return a value.

## Remarks

A camera's minidriver provides USBCAMD with the address of its <i>AdapterReceivePacket</i> function that processes SRBs in its call to the <b>USBCAMD_DriverEntry</b> service.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_driverentry.md">USBCAMD_DriverEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PADAPTER_RECEIVE_PACKET_ROUTINE callback function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>