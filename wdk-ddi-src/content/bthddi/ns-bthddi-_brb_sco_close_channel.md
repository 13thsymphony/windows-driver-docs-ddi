---
UID: NS.BTHDDI._BRB_SCO_CLOSE_CHANNEL
title: _BRB_SCO_CLOSE_CHANNEL
author: windows-driver-content
description: The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.
old-location: bltooth\_brb_sco_close_channel.htm
old-project: bltooth
ms.assetid: 1921cee1-411b-4fec-acfd-3380e84823b8
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BRB_SCO_CLOSE_CHANNEL,
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
req.alt-api: _BRB_SCO_CLOSE_CHANNEL
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

# _BRB_SCO_CLOSE_CHANNEL structure



## -description
The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.


## -syntax

````
struct _BRB_SCO_CLOSE_CHANNEL {
  BRB_HEADER         Hdr;
  BTH_ADDR           BtAddress;
  SCO_CHANNEL_HANDLE ChannelHandle;
};
````


## -struct-fields

### -field Hdr

A 
     <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The Bluetooth address of the remote device.

### -field ChannelHandle

The handle to the SCO channel to close.

## -remarks
To close a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536622">BRB_SCO_CLOSE_CHANNEL</a> request.

A <b>BRB_SCO_CLOSE_CHANNEL</b> request can be made for a channel that was initiated locally or remotely. If a
    profile driver has multiple SCO connections to a single remote device, it must close each one
    individually.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536622">BRB_SCO_CLOSE_CHANNEL</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_CLOSE_CHANNEL structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
