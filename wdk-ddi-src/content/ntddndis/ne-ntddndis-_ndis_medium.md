---
UID: NE.ntddndis._NDIS_MEDIUM
title: _NDIS_MEDIUM
author: windows-driver-content
description: The NDIS_MEDIUM enumeration type identifies the medium types that NDIS drivers support.
old-location: netvista\ndis_medium.htm
old-project: netvista
ms.assetid: 3e4aa7fb-0dd4-4c45-ab5e-21342e9fb4d8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_MEDIUM, NDIS_MEDIUM, *PNDIS_MEDIUM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MEDIUM
req.alt-loc: ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _NDIS_MEDIUM enumeration



## -description
The <b>NDIS_MEDIUM</b> enumeration type identifies the medium types that NDIS drivers support.


## -syntax

````
typedef enum _NDIS_MEDIUM { 
  NdisMedium802_3,
  NdisMedium802_5,
  NdisMediumFddi,
  NdisMediumWan,
  NdisMediumLocalTalk,
  NdisMediumDix,
  NdisMediumArcnetRaw,
  NdisMediumArcnet878_2,
  NdisMediumAtm,
  NdisMediumWirelessWan,
  NdisMediumIrda,
  NdisMediumBpc,
  NdisMediumCoWan,
  NdisMedium1394,
  NdisMediumInfiniBand,
#if ((NTDDI_VERSION >= NTDDI_VISTA) || NDIS_SUPPORT_NDIS6)
  NdisMediumTunnel,
  NdisMediumNative802_11,
  NdisMediumLoopback,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  NdisMediumIP,
#endif 
#endif 
  NdisMediumMax
} NDIS_MEDIUM, *PNDIS_MEDIUM;
````


## -enum-fields

### -field NdisMedium802_3

Specifies an Ethernet (802.3) network.

### -field NdisMedium802_5

Specifies a Token Ring (802.5) network.
<div class="alert"><b>Note</b>   Not supported in Windows 8 or later.</div>
<div> </div>

### -field NdisMediumFddi

Specifies a Fiber Distributed Data Interface (FDDI) network.
<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumWan

Specifies a wide area network. This type covers various forms of point-to-point and WAN NICs, as
     well as variant address/header formats that must be negotiated between the protocol driver and the
     underlying driver after the binding is established.

### -field NdisMediumLocalTalk

Specifies a LocalTalk network.

### -field NdisMediumDix

Specifies an Ethernet network for which the drivers use the DIX Ethernet header format.

### -field NdisMediumArcnetRaw

Specifies an ARCNET network.
<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumArcnet878_2

Specifies an ARCNET (878.2) network.
<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumAtm

Specifies an ATM network. Connection-oriented client protocol drivers can bind themselves to an
     underlying miniport driver that returns this value. Otherwise, legacy protocol drivers bind themselves
     to the system-supplied LanE intermediate driver, which reports its medium type as either of 
     <b>NdisMedium802_3</b> or 
     <b>NdisMedium802_5</b>, depending on how the LanE driver is configured by the network
     administrator.

### -field NdisMediumWirelessWan

Specifies a wireless network. NDIS 5.X miniport drivers that support wireless LAN (WLAN) or
     wireless WAN (WWAN) packets declare their medium as 
     <b>NdisMedium802_3</b> and emulate Ethernet to higher-level NDIS drivers.
     

<div class="alert"><b>Note</b>  Starting with Windows 7, this media type is supported and can
      be used for Mobile Broadband.</div>
<div> </div>


### -field NdisMediumIrda

Specifies an infrared (IrDA) network.

### -field NdisMediumBpc

Specifies a broadcast PC network.

### -field NdisMediumCoWan

Specifies a wide area network in a connection-oriented environment.

### -field NdisMedium1394

Specifies an IEEE 1394 (fire wire) network. 
<div class="alert"><b>Note</b>   Not supported in Windows Vista/Windows Server 2008 or later.</div>
<div> </div>

### -field NdisMediumInfiniBand

Specifies an InfiniBand network.

### -field NdisMediumTunnel

Specifies a tunnel network.

### -field NdisMediumNative802_11

Specifies a native IEEE 802.11 network.

### -field NdisMediumLoopback

Specifies an NDIS loopback network.

### -field NdisMediumIP

Specifies a generic medium that is capable of sending and receiving raw IP packets.

### -field NdisMediumMax

A maximum value for testing purposes.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 5.1, and NDIS 6.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ntddndis.h)</dt>
</dl>
</td>
</tr>
</table>