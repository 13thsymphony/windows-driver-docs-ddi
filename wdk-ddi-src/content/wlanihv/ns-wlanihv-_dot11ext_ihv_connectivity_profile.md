---
UID: NS:wlanihv._DOT11EXT_IHV_CONNECTIVITY_PROFILE
title: "_DOT11EXT_IHV_CONNECTIVITY_PROFILE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_connectivity_profile.htm
old-project: netvista
ms.assetid: 56ef9b59-5dbb-4720-bae1-7af6d9dbc110
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11EXT_IHV_CONNECTIVITY_PROFILE structure [Network Drivers Starting with Windows Vista], netvista.dot11ext_ihv_connectivity_profile, Native_802.11_data_types_a0d8e30b-4a72-44d2-a83a-c7b1785f2c8e.xml, wlanihv/PDOT11EXT_IHV_CONNECTIVITY_PROFILE, DOT11EXT_IHV_CONNECTIVITY_PROFILE, wlanihv/DOT11EXT_IHV_CONNECTIVITY_PROFILE, PDOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE, PDOT11EXT_IHV_CONNECTIVITY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_CONNECTIVITY_PROFILE
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
-	DOT11EXT_IHV_CONNECTIVITY_PROFILE
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_CONNECTIVITY_PROFILE structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_CONNECTIVITY_PROFILE structure specifies connectivity settings for the IHV
  profile.

## Syntax
````
typedef struct _DOT11EXT_IHV_CONNECTIVITY_PROFILE {
  LPWSTR pszXmlFragmentIhvConnectivity;
} DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE;
````

## Members


`pszXmlFragmentIhvConnectivity`

A pointer to the string that defines the IHV connectivity profile.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wlanihv.h (include Wlanihv.h) |