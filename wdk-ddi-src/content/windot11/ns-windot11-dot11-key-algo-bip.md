---
UID: NS.windot11.DOT11_KEY_ALGO_BIP
title: DOT11_KEY_ALGO_BIP
author: windows-driver-content
description: The DOT11_KEY_ALGO_BIP structure defines a cipher key that is used by the Broadcast Integrity Protocol (BIP) algorithm for management frame integrity protection.
old-location: netvista\dot11_key_algo_bip.htm
old-project: netvista
ms.assetid: 608AD247-19C8-40E8-B2FF-D49818AE4AD7
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: DOT11_KEY_ALGO_BIP, DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_KEY_ALGO_BIP
req.alt-loc: windot11.h
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
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_KEY_ALGO_BIP structure



## -description

## -syntax

````
typedef struct _DOT11_KEY_ALGO_BIP {
  UCHAR ucIPN[6];
  ULONG ulBIPKeyLength;
  UCHAR ucBIPKey[1];
} DOT11_KEY_ALGO_BIP, *PDOT11_KEY_ALGO_BIP;
````


## -struct-fields
<dl>

### -field <b>ucIPN[6]</b>

<dd>
<p>The initial IGTK packet number (IPN) used for replay protection.</p>
</dd>

### -field <b>ulBIPKeyLength</b>

<dd>
<p>The length, in bytes, of the BIP key material in <b>ucBIPKey</b> array.</p>
</dd>

### -field <b>ucBIPKey[1]</b>

<dd>
<p>The BIP key material.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 8 and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>