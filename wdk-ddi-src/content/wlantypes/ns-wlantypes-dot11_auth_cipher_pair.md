---
UID: NS:wlantypes.DOT11_AUTH_CIPHER_PAIR
title: DOT11_AUTH_CIPHER_PAIR
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_auth_cipher_pair.htm
old-project: netvista
ms.assetid: 301e9c21-69e7-48d3-b170-de01684f4a12
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_AUTH_CIPHER_PAIR structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_84940691-1e26-4039-927d-e1f1e0d14ea1.xml, wlantypes/PDOT11_AUTH_CIPHER_PAIR, wlantypes/DOT11_AUTH_CIPHER_PAIR, netvista.dot11_auth_cipher_pair, PDOT11_AUTH_CIPHER_PAIR structure pointer [Network Drivers Starting with Windows Vista], *PDOT11_AUTH_CIPHER_PAIR, PDOT11_AUTH_CIPHER_PAIR, DOT11_AUTH_CIPHER_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlantypes.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlantypes.h
apiname:
-	DOT11_AUTH_CIPHER_PAIR
product: Windows
targetos: Windows
req.typenames: DOT11_AUTH_CIPHER_PAIR, *PDOT11_AUTH_CIPHER_PAIR
req.product: Windows 10 or later.
---

# DOT11_AUTH_CIPHER_PAIR structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_AUTH_CIPHER_PAIR structure defines a pair of 802.11 authentication and cipher algorithms
  that can be enabled at the same time on the 802.11 station.

## Syntax
````
typedef struct DOT11_AUTH_CIPHER_PAIR {
  DOT11_AUTH_ALGORITHM   AuthAlgoId;
  DOT11_CIPHER_ALGORITHM CipherAlgoId;
} DOT11_AUTH_CIPHER_PAIR, *PDOT11_AUTH_CIPHER_PAIR;
````

## Members


`AuthAlgoId`

An authentication algorithm as specified by a 
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a> value.

`CipherAlgoId`

A cipher algorithm as specified by a 
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> value.

## Remarks
The DOT11_AUTH_CIPHER_PAIR structure defines an authentication and cipher algorithm that can be
    enabled together for basic service set (BSS) network connections.

A miniport driver returns a list of these structures when either 
    <a href="https://msdn.microsoft.com/en-us/library/gg157261.aspx">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a> is queried.

Starting with Windows 7, an 802.11 miniport driver can report any combination of supported
    authentication and cipher algorithm pairs in the 
    <a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">
    DOT11_AUTH_CIPHER_PAIR_LIST</a> structure. However, if the operating system starts Soft AP, it enables
    only the 
    <b>DOT11_AUTH_ALGO_RSNA_PSK</b> authentication algorithm and the 
    <b>DOT11_CIPHER_ALGO_CCMP</b> cipher algorithm. To support Soft AP, the miniport driver must support this
    authentication/cipher pair.<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://msdn.microsoft.com/library/windows/hardware/mt244265">Wi-Fi Direct</a>.</div>
<div> </div>


If WPS is enabled on a NIC that is operating in Extensible AP mode, the miniport driver must allow
    peer stations to associate with the Extensible AP by using 
    <a href="https://msdn.microsoft.com/f07d2d77-ccaf-4599-b59e-6ea4ecf55e0f">Open System Authentication</a> or 
    <a href="https://msdn.microsoft.com/41dd280b-e54c-4233-8051-45e7b1284d1d">Wired Equivalent Privacy (WEP)</a> algorithms, regardless of
    the enabled authorization and cipher algorithms. For more information about WPS and Extensible AP, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569436">OID_DOT11_WPS_ENABLED</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wlantypes.h (include Ndis.h) |

## See Also

<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>

<a href="..\windot11\ns-windot11-dot11_auth_cipher_pair_list.md">DOT11_AUTH_CIPHER_PAIR_LIST</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>

<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>

<a href="https://msdn.microsoft.com/en-us/library/gg157261.aspx">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_AUTH_CIPHER_PAIR structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>