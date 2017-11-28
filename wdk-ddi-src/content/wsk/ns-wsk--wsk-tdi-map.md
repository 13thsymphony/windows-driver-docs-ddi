---
UID: NS.wsk._WSK_TDI_MAP
title: WSK_TDI_MAP
author: windows-driver-content
description: The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and protocol to the device name of a TDI transport.
old-location: netvista\wsk_tdi_map.htm
old-project: netvista
ms.assetid: 4c1407e9-2e4d-41cc-8d50-017c8c2bf20f
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WSK_TDI_MAP, WSK_TDI_MAP, *PWSK_TDI_MAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_TDI_MAP
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WSK_TDI_MAP structure



## -description
<p>The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and
  protocol to the device name of a 
  <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.</p>


## -syntax

````
typedef struct _WSK_TDI_MAP {
  USHORT         SocketType;
  ADDRESS_FAMILY AddressFamily;
  ULONG          Protocol;
  PCWSTR         TdiDeviceName;
} WSK_TDI_MAP, *PWSK_TDI_MAP;
````


## -struct-fields
<dl>

### -field <b>SocketType</b>

<dd>
<p>The socket type. This member can contain any of the SOCK_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.</p>
</dd>

### -field <b>AddressFamily</b>

<dd>
<p>The address family. This member can contain any of the AF_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.</p>
</dd>

### -field <b>Protocol</b>

<dd>
<p>The transport protocol.</p>
</dd>

### -field <b>TdiDeviceName</b>

<dd>
<p>A pointer to a null-terminated wide character string that contains the device name for the 
     <a href="https://msdn.microsoft.com/7c432f72-4de6-40a8-884c-26e13926e550">TDI</a> transport that supports the combination of
     address family, socket type, and protocol specified by the 
     <b>AddressFamily</b>, 
     <b>SocketType</b>, and 
     <b>Protocol</b> members.</p>
</dd>
</dl>

## -remarks
<p>The 
    <b>Map</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571192">WSK_TDI_MAP_INFO</a> structure points to an
    array of WSK_TDI_MAP structures, each of which contains a mapping between a particular address family,
    socket type, and protocol to the device name of a 
    <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.</p>

<p>For more information about using TDI transports, see 
    <a href="NULL">Using TDI Transports</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571192">WSK_TDI_MAP_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_TDI_MAP structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
