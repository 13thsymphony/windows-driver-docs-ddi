---
UID: NS:wlanihvtypes._DOT11EXT_IHV_PROFILE_PARAMS
title: "_DOT11EXT_IHV_PROFILE_PARAMS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_profile_params.htm
old-project: netvista
ms.assetid: 9bf4b27c-3cf0-45a0-9e56-b01ad1ba6b19
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11EXT_IHV_PROFILE_PARAMS, DOT11EXT_IHV_PROFILE_PARAMS structure [Network Drivers Starting with Windows Vista], wlanihvtypes/DOT11EXT_IHV_PROFILE_PARAMS, PDOT11EXT_IHV_PROFILE_PARAMS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11ext_ihv_profile_params, *PDOT11EXT_IHV_PROFILE_PARAMS, _DOT11EXT_IHV_PROFILE_PARAMS, Native_802.11_data_types_3fe01c80-477b-4851-8b7e-4d4540cc22b6.xml, PDOT11EXT_IHV_PROFILE_PARAMS, wlanihvtypes/PDOT11EXT_IHV_PROFILE_PARAMS
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
-	wlanihvtypes.h
apiname:
-	DOT11EXT_IHV_PROFILE_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PDOT11EXT_IHV_PROFILE_PARAMS, DOT11EXT_IHV_PROFILE_PARAMS"
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_PROFILE_PARAMS structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_PROFILE_PARAMS structure specifies the general parameters of a basic service set
  (BSS) network with which a network profile will be applied.

## Syntax
````
typedef struct _DOT11EXT_IHV_PROFILE_PARAMS {
  PDOT11EXT_IHV_SSID_LIST    pSsidList;
  DOT11_BSS_TYPE             BssType;
  PDOT11_MSSECURITY_SETTINGS pMSSecuritySettings;
} DOT11EXT_IHV_PROFILE_PARAMS, *PDOT11EXT_IHV_PROFILE_PARAMS;
````

## Members


`BssType`

The type of the BSS network. The 
     <b>BssType</b> member contains a value defined for the 
     <a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a> enumeration.

`pMSSecuritySettings`

A pointer to a 
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11_mssecurity_settings.md">
     DOT11_MSSECURITY_SETTINGS</a> structure that defines Microsoft security settings in the Microsoft
     802.1X implementation.

`pSsidList`

A pointer to the list of service set identifiers (SSIDs) of the basic service set (BSS) network.
     The 
     <b>pSsidList</b> member is formatted as a pointer to a 
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_ssid_list.md">
     DOT11EXT_IHV_SSID_LIST</a> structure.

## Remarks
The operating system passes a pointer to a DOT11EXT_IHV_PROFILE_PARAMS structure as a parameter to any
    IHV handler function that processes the IHV-defined fragments of connectivity and security profiles. For
    more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
    Functions</a>.

Although the IHV handler function cannot access the entire network profile, the function can access
    the general attributes of the profile through the DOT11EXT_IHV_PROFILE_PARAMS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wlanihvtypes.h (include Wlanihv.h) |

## See Also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
   Dot11ExtIhvPerformCapabilityMatch</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>

<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_ssid_list.md">DOT11EXT_IHV_SSID_LIST</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_validate_profile.md">Dot11ExtIhvValidateProfile</a>

<a href="https://msdn.microsoft.com/de353aec-4339-496d-9aff-033b73f5d78e">
   IDot11ExtUIProperty::Dot11ExtUIPropertyGetDisplayInfo</a>

<a href="https://msdn.microsoft.com/fe136eef-4cc7-4a78-a5df-5f6c63a5007b">
   IDot11ExtUIProperty::Dot11ExtUIPropertySetDisplayInfo</a>

<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11_mssecurity_settings.md">DOT11_MSSECURITY_SETTINGS</a>

<a href="..\wlantypes\ne-wlantypes-_dot11_bss_type.md">DOT11_BSS_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_PROFILE_PARAMS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>