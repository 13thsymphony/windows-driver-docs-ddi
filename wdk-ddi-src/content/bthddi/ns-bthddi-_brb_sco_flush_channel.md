---
UID : NS:bthddi._BRB_SCO_FLUSH_CHANNEL
title : _BRB_SCO_FLUSH_CHANNEL
author : windows-driver-content
description : The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel.
old-location : bltooth\_brb_sco_flush_channel.htm
old-project : bltooth
ms.assetid : 17ee1a71-2aaf-421d-9ae9-019fe0d2f595
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth._brb_sco_flush_channel, _BRB_SCO_FLUSH_CHANNEL structure [Bluetooth Devices], bth_structs_d2a9941d-7091-402d-87bc-a5da139dfc1f.xml, bthddi/_BRB_SCO_FLUSH_CHANNEL, _BRB_SCO_FLUSH_CHANNEL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Windows
req.target-min-winverclnt : Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---

# _BRB_SCO_FLUSH_CHANNEL structure
The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel.

## Syntax
````
struct _BRB_SCO_FLUSH_CHANNEL {
  BRB_HEADER         Hdr;
  BTH_ADDR           BtAddress;
  SCO_CHANNEL_HANDLE ChannelHandle;
  ULONG              FlushFlags;
};
````

## Members


`BtAddress`

The Bluetooth address of the remote device.

`ChannelHandle`

The handle to the SCO channel to flush.

`FlushFlags`



`Hdr`

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.

## Remarks
To flush a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536623">BRB_SCO_FLUSH_CHANNEL</a> request.

All pending data transfer IRPs will be completed with STATUS_REQUEST_ABORTED. In-progress IRPs will be
    completed normally, with success or failure, depending on whether the Bluetooth driver stack was able to
    transfer data to or from the remote device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536623">BRB_SCO_FLUSH_CHANNEL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_FLUSH_CHANNEL structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>