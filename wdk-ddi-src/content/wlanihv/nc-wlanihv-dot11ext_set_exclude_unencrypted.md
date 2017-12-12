---
UID: NC.wlanihv.DOT11EXT_SET_EXCLUDE_UNENCRYPTED
title: DOT11EXT_SET_EXCLUDE_UNENCRYPTED
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetexcludeunencrypted.htm
old-project: netvista
ms.assetid: b6482124-0d65-4953-8a8f-a09c0a88d830
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _BINARY_CONTAINER, BINARY_CONTAINER, *PBINARY_CONTAINER
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
req.alt-api: Dot11ExtSetExcludeUnencrypted
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

# DOT11EXT_SET_EXCLUDE_UNENCRYPTED callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetExcludeUnencrypted(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     BOOL   bExcludeUnencrypted
);
````


## -parameters

### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param bExcludeUnencrypted [in]

A Boolean value that, if set to <b>TRUE</b>, configures the WLAN adapter to exclude unencrypted
     packets.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
If the WLAN adapter is enabled to exclude unencrypted packets, the station must exempt received
    packets that match an entry in the station's current EtherType exemption list. The IHV Extensions DLL
    specifies the EtherType exemption list through calls to the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
    Dot11ExtSetEtherTypeHandling</a> function.

A call to the 
    <b>Dot11ExtSetExcludeUnencrypted</b> function results in a set request of the 
    <a href="netvista.oid_dot11_exclude_unencrypted">
    OID_DOT11_EXCLUDE_UNENCRYPTED</a> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.


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
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569365">OID_DOT11_EXCLUDE_UNENCRYPTED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_EXCLUDE_UNENCRYPTED callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

