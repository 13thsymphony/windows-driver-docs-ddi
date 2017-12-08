---
UID: NS.BTHDDI._BRB_L2CA_PING
title: _BRB_L2CA_PING
author: windows-driver-content
description: The _BRB_L2CA_PING structure describes a request to ping a remote radio.
old-location: bltooth\_brb_l2ca_ping.htm
old-project: bltooth
ms.assetid: 699d2ea6-3bf3-457c-b05e-c45ec4c71fb6
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BRB_L2CA_PING,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _BRB_L2CA_PING
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
---

# _BRB_L2CA_PING structure



## -description
The _BRB_L2CA_PING structure describes a request to ping a remote radio.


## -syntax

````
struct _BRB_L2CA_PING {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
  UCHAR      PingRequestLength;
  UCHAR      PingRequestData[MAX_L2CAP_PING_DATA_LENGTH];
  UCHAR      PingResponseLength;
  UCHAR      PingResponseData[MAX_L2CAP_PING_DATA_LENGTH];
};
````


## -struct-fields

### -field Hdr

A 
     <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The address of the device that the ping is sent to.

### -field PingRequestLength

The length, in bytes, of the data to send in the ping signal.

### -field PingRequestData

The data to send in the ping signal.

### -field PingResponseLength

The length, in bytes, of the data that the remote device responded to the ping signal with.

### -field PingResponseData

The data that the remote device responded to the ping signal with.

## -remarks
To ping a remote radio, by transmitting a L2CA_EchoReq message and receiving a L2CAP_EchoRsp message,
    profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536617">BRB_L2CA_PING</a> request.

BRB_L2CA_PING is primarily used for debugging.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="bltooth.brb_header">BRB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536617">BRB_L2CA_PING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_PING structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
