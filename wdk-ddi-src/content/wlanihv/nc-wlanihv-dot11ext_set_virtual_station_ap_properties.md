---
UID: NC:wlanihv.DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
title: DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetvirtualstationapproperties.htm
old-project: netvista
ms.assetid: 11ba5799-2bb5-475f-bf69-cf1a1c3c128c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES, Dot11ExtSetVirtualStationAPProperties, Dot11ExtSetVirtualStationAPProperties callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_99551e02-eec3-413e-a14d-60d6ce5c09ee.xml, netvista.dot11extsetvirtualstationapproperties, wlanihv/Dot11ExtSetVirtualStationAPProperties
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtSetVirtualStationAPProperties
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---


# DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetVirtualStationAPProperties</b> function to specify the current IHV
  profile connection.

## Syntax

```
DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES Dot11extSetVirtualStationApProperties;

DWORD Dot11extSetVirtualStationApProperties(
  HANDLE hDot11SvcHandle,
  HANDLE hConnectSession,
  DWORD dwNumProperties,
  PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY pProperties,
  LPVOID pvReserved
)
{...}
```

## Parameters

`hDot11SvcHandle`

An optional handle used by the operating system to reference the primary physical wireless LAN
     (WLAN) adapter. This handle value was received as the 
     <i>hDot11SvcHandle</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`hConnectSession`

The handle used by the operating system to reference the current connection session with the basic
     service set (BSS) network. This handle value was received as the 
     <i>hConnectSession</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.

`dwNumProperties`

The number of elements in the array of structures pointed to by the 
     <i>pProperties</i> parameter.

`pProperties`

A pointer to an array of 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_virtual_station_ap_property.md">
     DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a> structures that specify the properties of access points (APs)
     that the virtual 802.11 station is attempting to host in the current connection session.

`pvReserved`

This parameter is reserved for use by the operating system and should be <b>NULL</b>.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

If the current IHV profile connection is an access point (AP), and the IHV Extensions DLL can provide
    to the operating system the settings used by the AP, the operating system can provide additional
    information to users who request AP-related service from the operating system.

If the IHV Extensions DLL calls 
    <b>Dot11ExtSetVirtualStationAPProperties</b>, it must do so before it calls the
    
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
    Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. If 
    <b>Dot11ExtSetVirtualStationAPProperties</b> is not called before successful
    completion of the pre-association operation, the operating system makes no assumptions about the nature
    of the IHV profile.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating   systems.  |
| **Target Platform** | Desktop |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_virtual_station_ap_property.md">
   DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>