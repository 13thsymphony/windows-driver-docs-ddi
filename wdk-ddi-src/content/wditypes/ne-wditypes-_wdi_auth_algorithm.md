---
UID: NE:wditypes._WDI_AUTH_ALGORITHM
title: _WDI_AUTH_ALGORITHM
author: windows-driver-content
description: The WDI_AUTH_ALGORITHM enumeration defines the authentication algorithm values.
old-location: netvista\wdi_auth_algorithm.htm
old-project: netvista
ms.assetid: B908A174-F977-484E-A086-6C8C9A914D6C
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WDI_AUTH_ALGORITHM, WDI_AUTH_ALGORITHM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_AUTH_ALGORITHM
req.alt-loc: wditypes.hpp
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
req.typenames: WDI_AUTH_ALGORITHM
req.product: Windows 10 or later.
---

# _WDI_AUTH_ALGORITHM enumeration



## -description
The WDI_AUTH_ALGORITHM enumeration defines the authentication algorithm values.



## -syntax

````
typedef enum _WDI_AUTH_ALGORITHM { 
  WDI_AUTH_ALGO_80211_OPEN        = 1,
  WDI_AUTH_ALGO_80211_SHARED_KEY  = 2,
  WDI_AUTH_ALGO_WPA               = 3,
  WDI_AUTH_ALGO_WPA_PSK           = 4,
  WDI_AUTH_ALGO_WPA_NONE          = 5,
  WDI_AUTH_ALGO_RSNA              = 6,
  WDI_AUTH_ALGO_RSNA_PSK          = 7,
  WDI_AUTH_ALGO_IHV_START         = 0x80000000,
  WDI_AUTH_ALGO_IHV_END           = 0xffffffff
} WDI_AUTH_ALGORITHM;
````


## -enum-fields

### -field WDI_AUTH_ALGO_80211_OPEN

Specifies an IEEE 802.11 Open System authentication algorithm. 


### -field WDI_AUTH_ALGO_80211_SHARED_KEY

Specifies an IEEE 802.11 Shared Key authentication algorithm that requires the use of a pre-shared Wired Equivalent Privacy (WEP) key for the 802.11 authentication.


### -field WDI_AUTH_ALGO_WPA

Specifies a Wi-Fi Protected Access (WPA) algorithm. IEEE 802.1X port authorization is performed by the supplicant, authenticator, and authentication server. Cipher keys are dynamically derived through the authentication process. 

When the WPA algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 1 (802.1X) within the WPA information element (IE).


### -field WDI_AUTH_ALGO_WPA_PSK

Specifies a Wi-Fi Protected Access (WPA) algorithm that uses preshared keys (PSK). IEEE 802.1X port authorization is performed by the supplicant and authenticator. Cipher keys are dynamically derived through a preshared key that is used on both the supplicant and authenticator. 

When the WPA PSK algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the WPA IE.


### -field WDI_AUTH_ALGO_WPA_NONE

This value is not supported.


### -field WDI_AUTH_ALGO_RSNA

Specifies an IEEE 802.11i Robust Security Network Association (RSNA) algorithm. IEEE 802.1X port authorization is performed by the supplicant, authenticator, and authentication server. Cipher keys are dynamically derived through the authentication process. 

When the RSNA algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 1 (802.1X) within the Robust Security Network (RSN) IE.


### -field WDI_AUTH_ALGO_RSNA_PSK

Specifies an IEEE 802.11i RSNA algorithm that uses PSK. IEEE 802.1X port authorization is performed by the supplicant and authenticator. Cipher keys are dynamically derived through a pre-shared key that is used on both the supplicant and authenticator. 

When the RSNA PSK algorithm is enabled, the 802.11 station only associates with an access point whose beacon or probe responses contain the authentication suite of type 2 (preshared key) within the RSN IE.


### -field WDI_AUTH_ALGO_IHV_START

Specifies the start of the range that specifies proprietary authentication algorithms that are developed by an IHV. 


### -field WDI_AUTH_ALGO_IHV_END

Specifies the end of the range that specifies proprietary authentication algorithms that are developed by an IHV. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>