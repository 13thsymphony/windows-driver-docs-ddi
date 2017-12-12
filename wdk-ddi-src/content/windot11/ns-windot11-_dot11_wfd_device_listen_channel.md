---
UID: NS.WINDOT11._DOT11_WFD_DEVICE_LISTEN_CHANNEL
title: _DOT11_WFD_DEVICE_LISTEN_CHANNEL
author: windows-driver-content
description: The DOT11_WFD_DEVICE_LISTEN_CHANNEL structure describes the Wi-Fi Direct device's listen channel when responding to a OID_DOT11_WFD_DEVICE_LISTEN_CHANNEL set or query request.
old-location: netvista\dot11_wfd_device_listen_channel.htm
old-project: netvista
ms.assetid: F493F295-A133-454B-99AD-E216D105E707
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DOT11_WFD_DEVICE_LISTEN_CHANNEL, *PDOT11_WFD_DEVICE_LISTEN_CHANNEL, DOT11_WFD_DEVICE_LISTEN_CHANNEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_DEVICE_LISTEN_CHANNEL
req.alt-loc: Windot11.h
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
req.product: Windows 10 or later.
---

# _DOT11_WFD_DEVICE_LISTEN_CHANNEL structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_DEVICE_LISTEN_CHANNEL {
  NDIS_OBJECT_HEADER Header;
  UCHAR              ChannelNumber;
} DOT11_WFD_DEVICE_LISTEN_CHANNEL, *PDOT11_WFD_DEVICE_LISTEN_CHANNEL;
````


## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DEVICE_LISTEN_CHANNEL</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_DEVICE_LISTEN_CHANNEL_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DEVICE_LISTEN_CHANNEL_REVISION_1</td>
</tr>
</table>
 


### -field ChannelNumber

The device listen channel.   Windows may use <a href="https://msdn.microsoft.com/library/windows/hardware/hh738803">OID_DOT11_WFD_DEVICE_LISTEN_CHANNEL</a> to specify a listen channel (for example 1, 6, or 11). Wi-Fi Direct devices may treat this value as a hint to the device, which may adopt the specified channel, or continue to use the default listen channel. The Wi-Fi Direct device may also change the listen channel at any time.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh738803">OID_DOT11_WFD_DEVICE_LISTEN_CHANNEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_WFD_DEVICE_LISTEN_CHANNEL structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

