---
UID: NC.wlanihv.DOT11EXT_SET_AUTH_ALGORITHM
title: DOT11EXT_SET_AUTH_ALGORITHM
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetauthalgorithm.htm
old-project: netvista
ms.assetid: 49fbdd9d-4352-48b5-81bc-3092eef2e255
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PrintPropertyValue, PrintPropertyValue
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
req.alt-api: Dot11ExtSetAuthAlgorithm
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
req.iface: 
req.product: Windows 10 or later.
---

# DOT11EXT_SET_AUTH_ALGORITHM callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetAuthAlgorithm(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwAuthAlgo
);
````


## -parameters
<dl>

### -param <i>hDot11SvcHandle</i> [in, optional]

<dd>
<p>The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>

### -param <i>dwAuthAlgo</i> [in]

<dd>
<p>A 
     <a href="..\wlantypes\ne-wlantypes--dot11-auth-algorithm.md">DOT11_AUTH_ALGORITHM</a> enumerator value
     that identifies the authentication algorithm. 
     </p>
<p>If the value is within the range of <b>DOT11_AUTH_ALGO_IHV_START</b> through DOT11_AUTH_ALGO_IHV_END, the
     IHV Extensions DLL enables a proprietary authentication algorithm supported by the WLAN adapter.</p>
<p>Otherwise, the DLL is responsible for the processing of a standard authentication algorithm supported
     by the operating system. In this situation, the operating system is not involved with the authentication
     processing over a basic service set (BSS) network connection through the WLAN adapter.</p>
<p>
<div class="alert"><b>Note</b>  The value of 
      <i>dwAuthAlgo</i> must match the value of an authentication algorithm returned by the Native 802.11
      miniport driver through setting the appropriate <i>xxx</i><b>AlgoPairs</b> members of the  <a href="..\windot11\ns-windot11-dot11-extsta-attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure, which must match the values that would be returned by queries of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569430">OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569424">OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.</div>
<div> </div>
</p>
</dd>
</dl>

## -returns
<p>If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wlantypes\ne-wlantypes--dot11-auth-algorithm.md">DOT11_AUTH_ALGORITHM</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext-pre-associate-completion.md">
   Dot11ExtPreAssociateCompletion</a>
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
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_AUTH_ALGORITHM callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
