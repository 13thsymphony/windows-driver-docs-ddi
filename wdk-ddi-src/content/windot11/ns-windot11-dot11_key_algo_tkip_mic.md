---
UID: NS.WINDOT11.DOT11_KEY_ALGO_TKIP_MIC
title: DOT11_KEY_ALGO_TKIP_MIC
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_key_algo_tkip_mic.htm
old-project: NetVista
ms.assetid: 2f6e08e3-50cf-4d2e-aac8-185a5c0b38ed
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: DOT11_KEY_ALGO_TKIP_MIC, *PDOT11_KEY_ALGO_TKIP_MIC, DOT11_KEY_ALGO_TKIP_MIC, PDOT11_KEY_ALGO_TKIP_MIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_KEY_ALGO_TKIP_MIC
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
req.product: Windows 10 or later.
---

# DOT11_KEY_ALGO_TKIP_MIC structure



## -description

## -syntax

````
typedef struct DOT11_KEY_ALGO_TKIP_MIC {
  UCHAR ucIV48Counter[6];
  ULONG ulTKIPKeyLength;
  ULONG ulMICKeyLength;
  UCHAR ucTKIPMICKeys[1];
} DOT11_KEY_ALGO_TKIP_MIC, *PDOT11_KEY_ALGO_TKIP_MIC;
````


## -struct-fields

### -field ucIV48Counter

The initial 48-bit value of the TKIP Sequence Counter (TSC), which is used for replay protection.
     For more information about the TSC, see 
     <a href="https://msdn.microsoft.com/4f0c45f0-3125-4b19-82c1-3681b2e31c96">TKIP</a>.


### -field ulTKIPKeyLength

The length, in bytes, of the TKIP key material in the 
     <b>ucTKIPMICKeys</b> array. If the authentication and cipher key derivation is performed by the operating
     system, this member will always have a value of 16.


### -field ulMICKeyLength

The length, in bytes, of the MIC key material in the 
     <b>ucTKIPMICKeys</b> array. If the authentication and cipher key derivation is performed by the operating
     system, this member will always have a value of 16. The first 8 bytes will be the MIC key used for
     received packets and the last 8 bytes will be the MIC key used for transmitted packets.


### -field ucTKIPMICKeys

The TKIP and MIC key material.


## -remarks
The TKIP key starts at 
    <b>ucTKIPMICKeys</b> [0]. The MIC key starts at 
    <b>ucTKIPMICKeys</b> [
    <b>ulTKIPKeyLength</b> ].

When the TKIP key is created, the 802.11 station must maintain separate TSC counters for the key for
    the send and receive path. The station must initialize the TSC counters in the following way:

Initialize the TSC counter used for the receive path to the value specified in the 
      <b>ucIV48Counter</b> member.

Initialize the TSC counter used for the send path to any value.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
   DOT11_CIPHER_DEFAULT_KEY_VALUE</a>
</dt>
<dt>
<a href="netvista.oid_dot11_cipher_key_mapping_key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4f0c45f0-3125-4b19-82c1-3681b2e31c96">TKIP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_KEY_ALGO_TKIP_MIC structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

