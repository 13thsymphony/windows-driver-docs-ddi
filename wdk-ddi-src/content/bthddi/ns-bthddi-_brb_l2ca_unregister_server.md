---
UID: NS.BTHDDI._BRB_L2CA_UNREGISTER_SERVER
title: _BRB_L2CA_UNREGISTER_SERVER
author: windows-driver-content
description: A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices.
old-location: bltooth\_brb_l2ca_unregister_server.htm
old-project: bltooth
ms.assetid: bc10d76f-da09-457a-b469-ef59d1cb09d9
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BRB_L2CA_UNREGISTER_SERVER,
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
req.alt-api: _BRB_L2CA_UNREGISTER_SERVER
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

# _BRB_L2CA_UNREGISTER_SERVER structure



## -description
A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving L2CAP connections from remote Bluetooth devices.


## -syntax

````
struct _BRB_L2CA_UNREGISTER_SERVER {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
  PVOID      ServerHandle;
  USHORT     Psm;
};
````


## -struct-fields

### -field Hdr

A 
     <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The address of the remote device.

### -field ServerHandle

The handle of the L2CAP server to unregister, as returned earlier from a previous 
     <a href="bltooth.brb_l2ca_register_server">
     BRB_L2CA_REGISTER_SERVER</a> request.

### -field Psm

The Protocol/Service Multiplexer (PSM) that was specified in a previous 
     <a href="bltooth.brb_l2ca_register_server">
     BRB_L2CA_REGISTER_SERVER</a> request.

## -remarks
To unregister itself as a L2CAP server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="bltooth.brb_l2ca_unregister_server">
    BRB_L2CA_UNREGISTER_SERVER</a> request.

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
<a href="..\bthddi\ns-bthddi-_brb_l2ca_register_server.md">_BRB_L2CA_REGISTER_SERVER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536619">BRB_L2CA_UNREGISTER_SERVER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_UNREGISTER_SERVER structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
