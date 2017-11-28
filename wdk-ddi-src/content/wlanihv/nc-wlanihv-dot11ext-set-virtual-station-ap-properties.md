---
UID: NC.wlanihv.DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
title: DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetvirtualstationapproperties.htm
old-project: netvista
ms.assetid: 11ba5799-2bb5-475f-bf69-cf1a1c3c128c
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: PrintPropertyValue, PrintPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtSetVirtualStationAPProperties
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

# DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetVirtualStationAPProperties(
  _In_opt_   HANDLE                                hDot11SvcHandle,
  _In_opt_   HANDLE                                hConnectSession,
  _In_       DWORD                                 dwNumProperties,
  _In_       PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY pProperties,
  _Reserved_ LPVOID                                pvReserved
);
````


## -parameters
<dl>

### -param <i>hDot11SvcHandle</i> [in, optional]

<dd>
<p>An optional handle used by the operating system to reference the primary physical wireless LAN
     (WLAN) adapter. This handle value was received as the 
     <i>hDot11SvcHandle</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>

### -param <i>hConnectSession</i> [in, optional]

<dd>
<p>The handle used by the operating system to reference the current connection session with the basic
     service set (BSS) network. This handle value was received as the 
     <i>hConnectSession</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-perform-pre-associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.</p>
</dd>

### -param <i>dwNumProperties</i> [in]

<dd>
<p>The number of elements in the array of structures pointed to by the 
     <i>pProperties</i> parameter.</p>
</dd>

### -param <i>pProperties</i> [in]

<dd>
<p>A pointer to an array of 
     <a href="..\wlanihv\ns-wlanihv--dot11ext-virtual-station-ap-property.md">
     DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a> structures that specify the properties of access points (APs)
     that the virtual 802.11 station is attempting to host in the current connection session.</p>
</dd>

### -param <i>pvReserved</i> 

<dd>
<p>This parameter is reserved for use by the operating system and should be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.</p>

## -remarks
<p>If the current IHV profile connection is an access point (AP), and the IHV Extensions DLL can provide
    to the operating system the settings used by the AP, the operating system can provide additional
    information to users who request AP-related service from the operating system.</p>

<p>If the IHV Extensions DLL calls 
    <b>Dot11ExtSetVirtualStationAPProperties</b>, it must do so before it calls the
    
    <a href="..\wlanihv\nc-wlanihv-dot11extihv-perform-pre-associate.md">
    Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. If 
    <b>Dot11ExtSetVirtualStationAPProperties</b> is not called before successful
    completion of the pre-association operation, the operating system makes no assumptions about the nature
    of the IHV profile.</p>

<p>If the current IHV profile connection is an access point (AP), and the IHV Extensions DLL can provide
    to the operating system the settings used by the AP, the operating system can provide additional
    information to users who request AP-related service from the operating system.</p>

<p>If the IHV Extensions DLL calls 
    <b>Dot11ExtSetVirtualStationAPProperties</b>, it must do so before it calls the
    
    <a href="..\wlanihv\nc-wlanihv-dot11extihv-perform-pre-associate.md">
    Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. If 
    <b>Dot11ExtSetVirtualStationAPProperties</b> is not called before successful
    completion of the pre-association operation, the operating system makes no assumptions about the nature
    of the IHV profile.</p>

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
<p>Available in Windows 7 and later versions of the Windows operating
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
<a href="..\wlanihv\ns-wlanihv--dot11ext-virtual-station-ap-property.md">
   DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-perform-pre-associate.md">
   Dot11ExtIhvPerformPreAssociate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
