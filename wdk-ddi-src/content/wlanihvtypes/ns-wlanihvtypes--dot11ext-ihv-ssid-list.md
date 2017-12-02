---
UID: NS.wlanihvtypes._DOT11EXT_IHV_SSID_LIST
title: DOT11EXT_IHV_SSID_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_ssid_list.htm
old-project: netvista
ms.assetid: 10ef8868-5a65-4ed9-9f1d-440cda30cba4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DOT11EXT_IHV_SSID_LIST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihvtypes.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11EXT_IHV_SSID_LIST
req.alt-loc: wlanihvtypes.h
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

# DOT11EXT_IHV_SSID_LIST structure



## -description

## -syntax

````
typedef struct _DOT11EXT_IHV_SSID_LIST {
  ULONG      ulCount;
  DOT11_SSID SSIDs[1];
} DOT11EXT_IHV_SSID_LIST, *PDOT11EXT_IHV_SSID_LIST;
````


## -struct-fields
<dl>

### -field ulCount

<dd>
<p>The number of SSIDs in the list.</p>
</dd>

### -field SSIDs

<dd>
<p>An SSID of type 
     <a href="..\wlantypes\ns-wlantypes--dot11-ssid.md">DOT11_SSID</a>. This is the first SSID in the
     list.</p>
</dd>
</dl>

## -remarks
<p>An SSID is a string that identifies a set of interconnected basic service sets (BSSs).</p>

## -requirements
<table>
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
<dt>Wlanihvtypes.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wlantypes\ns-wlantypes--dot11-ssid.md">DOT11_SSID</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_SSID_LIST structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
