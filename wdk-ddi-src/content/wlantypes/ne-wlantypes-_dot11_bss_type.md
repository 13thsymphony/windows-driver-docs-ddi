---
UID: NE.wlantypes._DOT11_BSS_TYPE
title: _DOT11_BSS_TYPE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_type.htm
old-project: NetVista
ms.assetid: 5cb263e2-e5b7-456f-9fef-deaf5434c404
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_BSS_TYPE, *PDOT11_BSS_TYPE, DOT11_BSS_TYPE, PDOT11_BSS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wlantypes.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_BSS_TYPE
req.alt-loc: wlantypes.h
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

# _DOT11_BSS_TYPE enumeration



## -description

## -syntax

````
typedef enum _DOT11_BSS_TYPE { 
  dot11_BSS_type_infrastructure  = 1,
  dot11_BSS_type_independent     = 2,
  dot11_BSS_type_any             = 3
} DOT11_BSS_TYPE, *PDOT11_BSS_TYPE;
````


## -enum-fields

### -field dot11_BSS_type_infrastructure

Specifies an infrastructure BSS network.


### -field dot11_BSS_type_independent

Specifies an independent BSS (IBSS) network.


### -field dot11_BSS_type_any

Specifies either infrastructure or IBSS network.


## -remarks
The 
    <b>dot11_BSS_type_any</b> enumerator is valid only if it is specified when 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a> is set. 
    <b>dot11_BSS_type_any</b> is used to request a scan for all types of BSSs that are visible to the 802.11
    station.


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
<dt>Wlantypes.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11ext_ihv_profile_params">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_connection_start">
   NDIS_STATUS_DOT11_CONNECTION_START</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569142">OID_DOT11_DESIRED_BSS_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_BSS_TYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

