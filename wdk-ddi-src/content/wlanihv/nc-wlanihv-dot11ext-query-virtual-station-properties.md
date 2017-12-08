---
UID: NC.wlanihv.DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES
title: DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extqueryvirtualstationproperties.htm
old-project: netvista
ms.assetid: 4ea71ef7-c897-413c-a542-e8068bcc66a6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PrintPropertyValue, PrintPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtQueryVirtualStationProperties
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

# DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtQueryVirtualStationProperties(
  _In_opt_   HANDLE hDot11SvcHandle,
  _Out_      BOOL   *pbIsVirtualStation,
  _Out_      GUID   *pgPrimary,
  _Reserved_ LPVOID pvReserved
);
````


## -parameters
<dl>

### -param hDot11SvcHandle [in, optional]

<dd>
<p>A handle used by the operating system to reference the primary physical wireless LAN (WLAN)
     adapter. This handle value was received as the 
     <i>hDot11SvcHandle</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>

### -param pbIsVirtualStation [out]

<dd>
<p>A pointer to a Boolean value that indicates whether the primary physical WLAN adapter pointed to
     by the 
     <i>hDot11SvcHandle</i> parameter is a virtual station adapter or not. If the value is <b>TRUE</b>, the queried
     adapter is a virtual station, otherwise it is not a virtual station.</p>
</dd>

### -param pgPrimary [out]

<dd>
<p>A pointer to a GUID value that identifies the primary physical WLAN adapter that hosts a virtual
     station. This parameter is valid only if 
     <i>pbIsVirtualStation</i> points to a value that is <b>TRUE</b>.</p>
</dd>

### -param pvReserved 

<dd>
<p>This parameter is reserved for use by the operating system and should be <b>NULL</b>.</p>
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
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
