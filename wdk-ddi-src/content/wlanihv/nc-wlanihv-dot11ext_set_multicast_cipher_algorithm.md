---
UID: NC.wlanihv.DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM
title: DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetmulticastcipheralgorithm.htm
old-project: NetVista
ms.assetid: af023bc5-af3e-429c-b9c4-c06e5598cfaf
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _BINARY_CONTAINER, *PBINARY_CONTAINER, PBINARY_CONTAINER, BINARY_CONTAINER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtSetMulticastCipherAlgorithm
req.alt-loc: wlanihv.h
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

# DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetMulticastCipherAlgorithm(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwMulticastCipherAlgo
);
````


## -parameters

### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param dwMulticastCipherAlgo [in]

A 
     <a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a> enumerator
     value that identifies the multicast cipher algorithm. 
     

If the value is within the range of <b>DOT11_CIPHER_ALGO_IHV_START</b> through DOT11_CIPHER_ALGO_IHV_END,
     the IHV Extensions DLL enables a proprietary cipher algorithm supported by the WLAN adapter.

Otherwise, the DLL is responsible for processing a standard cipher algorithm supported by the
     operating system. In this situation, the operating system is not involved with any aspect of the cipher
     algorithm, including key management and replay protection, over a basic service set (BSS) network
     connection through the WLAN adapter.

<div class="alert"><b>Note</b>  The value of 
     <i>dwMulticastCipherAlgo</i> must match the value of a cipher algorithm returned by the Native 802.11
     miniport driver through setting the appropriate <i>xxx</i><b>AlgoPairs</b> members of the  <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure, which must match the values that would be returned by queries of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569430">OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569424">OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.</div>
<div> </div>

## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

