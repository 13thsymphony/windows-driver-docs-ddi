---
UID: NS:wlanihv._DOT11EXT_IHV_SECURITY_PROFILE
title: "_DOT11EXT_IHV_SECURITY_PROFILE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_security_profile.htm
old-project: netvista
ms.assetid: cbfeace3-6492-4011-9ca8-c40ba4f47d22
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wlanihv/DOT11EXT_IHV_SECURITY_PROFILE, Native_802.11_data_types_7761c811-0068-48d5-8b46-da550a008a9c.xml, *PDOT11EXT_IHV_SECURITY_PROFILE, PDOT11EXT_IHV_SECURITY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], PDOT11EXT_IHV_SECURITY_PROFILE, wlanihv/PDOT11EXT_IHV_SECURITY_PROFILE, DOT11EXT_IHV_SECURITY_PROFILE, _DOT11EXT_IHV_SECURITY_PROFILE, netvista.dot11ext_ihv_security_profile, DOT11EXT_IHV_SECURITY_PROFILE structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
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
-	wlanihv.h
apiname:
-	DOT11EXT_IHV_SECURITY_PROFILE
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_SECURITY_PROFILE structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_SECURITY_PROFILE structure specifies security settings for the IHV profile.

## Syntax
````
typedef struct _DOT11EXT_IHV_SECURITY_PROFILE {
  LPWSTR pszXmlFragmentIhvSecurity;
  BOOL   bUseMSOnex;
} DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE;
````

## Members


`bUseMSOnex`

A flag that indicates whether the IHV security profile is using the Microsoft 802.1X
     implementation. If <b>TRUE</b>, the profile uses the Microsoft 802.1X implementation.

`pszXmlFragmentIhvSecurity`

A pointer to the string that defines the IHV security profile.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wlanihv.h (include Wlanihv.h) |