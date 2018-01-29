---
UID : NS:wlanihv._WDIAG_IHV_WLAN_ID
title : _WDIAG_IHV_WLAN_ID
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\wdiag_ihv_wlan_id.htm
old-project : netvista
ms.assetid : 72dc7128-fcbc-4ad8-ac81-e2767ac6ffa2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wdiag_ihv_wlan_id, WDIAG_IHV_WLAN_ID, PWDIAG_IHV_WLAN_ID structure pointer [Network Drivers Starting with Windows Vista], wlanihv/WDIAG_IHV_WLAN_ID, wlanihv/PWDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID, PWDIAG_IHV_WLAN_ID, WDIAG_IHV_WLAN_ID structure [Network Drivers Starting with Windows Vista], _WDIAG_IHV_WLAN_ID, Native_802.11_data_types_25565f34-9a6d-4c59-908f-527c1d9a43b1.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID
req.product : Windows 10 or later.
---

# _WDIAG_IHV_WLAN_ID structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The WDIAG_IHV_WLAN_ID structure specifies an identifier used for error diagnostics on an IHV
  profile.

## Syntax
````
typedef struct _WDIAG_IHV_WLAN_ID {
  WCHAR          strProfileName[MS_MAX_PROFILE_NAME_LENGTH];
  DOT11_SSID     Ssid;
  DOT11_BSS_TYPE BssType;
  DWORD          dwFlags;
  DWORD          dwReasonCode;
} WDIAG_IHV_WLAN_ID, *PWDIAG_IHV_WLAN_ID;
````

## Members


`BssType`

The type of the BSS network. The 
     <b>BssType</b> member contains a value defined for the 
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration.

`dwFlags`

A flag which, if set to WDIAG_IHV_WLAN_ID_FLAG_SECURITY_ENABLED, indicates that security is
     enabled for this IHV profile. Otherwise, security is not enabled.

`dwReasonCode`

An error reason code, when available.

`Ssid`

The service set identifier (SSID) of the basic service set (BSS) network. The 
     <b>Ssid</b> member is of the 
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a> type.

`strProfileName`

A string that defines the IHV profile name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>

<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDIAG_IHV_WLAN_ID structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>