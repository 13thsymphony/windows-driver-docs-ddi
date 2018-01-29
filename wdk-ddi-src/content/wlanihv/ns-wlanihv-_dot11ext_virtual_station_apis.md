---
UID : NS:wlanihv._DOT11EXT_VIRTUAL_STATION_APIS
title : _DOT11EXT_VIRTUAL_STATION_APIS
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11ext_virtual_station_apis.htm
old-project : netvista
ms.assetid : 5487375a-7d50-4ddd-a666-8727f45b85dc
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PDOT11EXT_VIRTUAL_STATION_APIS structure pointer [Network Drivers Starting with Windows Vista], PDOT11EXT_VIRTUAL_STATION_APIS, netvista.dot11ext_virtual_station_apis, DOT11EXT_VIRTUAL_STATION_APIS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_0b2dadd3-7d60-4836-9171-c2c11b56010d.xml, *PDOT11EXT_VIRTUAL_STATION_APIS, wlanihv/PDOT11EXT_VIRTUAL_STATION_APIS, _DOT11EXT_VIRTUAL_STATION_APIS, wlanihv/DOT11EXT_VIRTUAL_STATION_APIS, DOT11EXT_VIRTUAL_STATION_APIS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames : "*PDOT11EXT_VIRTUAL_STATION_APIS, DOT11EXT_VIRTUAL_STATION_APIS"
req.product : Windows 10 or later.
---

# _DOT11EXT_VIRTUAL_STATION_APIS structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_VIRTUAL_STATION_APIS structure specifies a list of pointers to the IHV Extensibility
  virtual station functions that are supported by the operating system.

## Syntax
````
typedef struct _DOT11EXT_VIRTUAL_STATION_APIS {
  DOT11EXT_REQUEST_VIRTUAL_STATION           Dot11ExtRequestVirtualStation;
  DOT11EXT_RELEASE_VIRTUAL_STATION           Dot11ExtReleaseVirtualStation;
  DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES  Dot11ExtQueryVirtualStationProperties;
  DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES Dot11ExtSetVirtualStationAPProperties;
} DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS;
````

## Members


## Remarks
The IHV Extensibility virtual station functions are not statically or dynamically linked to the IHV
    Extensions DLL. Instead, when the operating system calls the 
    <mshelp:link keywords="netvista.dot11extihvinitvirtualstation" tabindex="0"><i>
    Dot11ExtIhvInitVirtualStation</i></mshelp:link> IHV handler function, it passes the list of pointers to the IHV
    Extensibility functions through the 
    <i>pDot11ExtVSAPI</i> parameter.
<div class="alert"><b>Note</b>  The IHV Extensions DLL is allowed to call the virtual station API functions that
    the 
    <i>pDot11ExtVSAPI</i> parameter points to only after the 
    <mshelp:link keywords="netvista.dot11extihvinitvirtualstation" tabindex="0"><i>
    Dot11ExtIhvInitVirtualStation</i></mshelp:link> function returns.</div><div> </div>All of the function pointers are required and must not be set to <b>NULL</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<mshelp:link keywords="netvista.dot11extsetvirtualstationapproperties" tabindex="0"><b>
   Dot11ExtSetVirtualStationAPProperties</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extqueryvirtualstationproperties" tabindex="0"><b>
   Dot11ExtQueryVirtualStationProperties</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extreleasevirtualstation" tabindex="0"><b>
   Dot11ExtReleaseVirtualStation</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extrequestvirtualstation" tabindex="0"><b>
   Dot11ExtRequestVirtualStation</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extihvinitvirtualstation" tabindex="0"><i>
   Dot11ExtIhvInitVirtualStation</i></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_VIRTUAL_STATION_APIS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>