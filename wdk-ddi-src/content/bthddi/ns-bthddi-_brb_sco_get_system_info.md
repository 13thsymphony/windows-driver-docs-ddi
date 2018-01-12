---
UID: NS:bthddi._BRB_SCO_GET_SYSTEM_INFO
title: _BRB_SCO_GET_SYSTEM_INFO
author: windows-driver-content
description: The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO connections.
old-location: bltooth\_brb_sco_get_system_info.htm
old-project: bltooth
ms.assetid: f8afda8b-12de-4955-8f25-0b2dae031ff1
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BRB_SCO_GET_SYSTEM_INFO,
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
req.alt-api: _BRB_SCO_GET_SYSTEM_INFO
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
req.typenames: 
---

# _BRB_SCO_GET_SYSTEM_INFO structure



## -description
The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO
  connections.



## -syntax

````
struct _BRB_SCO_GET_SYSTEM_INFO {
  BRB_HEADER Hdr;
  ULONG      Features;
  ULONG      MaxChannels;
  ULONG      TransferUnit;
  USHORT     PacketTypes;
  USHORT     DataFormats;
  ULONG      Reserved;
};
````


## -struct-fields

### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field Features

A flag or combination of flags that indicates what SCO features the system supports. Possible
     values include:
     



### -field SCO_FEATURE_ESCO_LINKS
     

### -field SCO_FEATURE_SCO_LINKS




### -field MaxChannels

The maximum number of active SCO channels that the system supports. This member is set to 0xFFFF
     if there is no limit or if the limit is unknown.


### -field TransferUnit

The minimum data transfer speed per each request, in milliseconds . Set to 0xFFFF if this value is
     variable or unknown.


### -field PacketTypes

A flag or combination of flags that indicates the type of SCO data packets that the local system
     supports. These SCO packet types are defined by the Bluetooth SIG. See the Bluetooth specification for
     more information about these flags. Possible values include:
     



### -field SCO_HV1
     

### -field SCO_HV2
     

### -field SCO_HV3
     

### -field SCO_EV3
     

### -field SCO_EV4
     

### -field SCO_EV5




### -field DataFormats

A flag or combination of flags the indicates the voice-encoding data formats supported by the
     local system. Possible values include:
     



### -field SCO_DATA_FORMAT_A_LAW_LOG 
     

### -field SCO_DATA_FORMAT_CVSD
     

### -field SCO_DATA_FORMAT_MU_LAW_LOG
     

### -field SCO_DATA_FORMAT_TRANSPARENT




### -field Reserved

Reserved for future use. Do not use.


## -remarks
To get the local system's support for SCO connections, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536625">BRB_SCO_GET_SYSTEM_INFO</a> request.

Higher-level profile drivers can build and send a <b>BRB_SCO_GET_SYSTEM_INFO</b> request to determine whether
    the local Bluetooth driver stack supports SCO connections, the maximum number of SCO channels that the
    system supports, and other useful information for opening a SCO connection to a remote device.


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
<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536625">BRB_SCO_GET_SYSTEM_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_GET_SYSTEM_INFO structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

