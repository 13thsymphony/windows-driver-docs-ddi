---
UID : NC:wlanihv.DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
title : DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11extsetprofilecustomuserdata.htm
old-project : netvista
ms.assetid : 25e1462c-6eaa-480a-9f9e-6f8689da05c5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.dot11extsetprofilecustomuserdata, Dot11ExtSetProfileCustomUserData callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetProfileCustomUserData, DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA, DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA, wlanihv/Dot11ExtSetProfileCustomUserData, Native_802.11_IHV_Ext_87f713b8-bd3e-4165-adce-c37fbb829cdb.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Desktop
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
req.typenames : "*LPDRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W"
req.product : Windows 10 or later.
---


# DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetProfileCustomUserData</b> function to save data within the system
  registry that is specific to the current user and network profile used for the basic service set (BSS)
  network connection.

## Syntax

```
DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA Dot11extSetProfileCustomUserData;

DWORD Dot11extSetProfileCustomUserData(
  HANDLE hDot11SvcHandle,
  HANDLE hConnectSession,
  DWORD dwSessionID,
  DWORD dwDataSize,
  LPVOID pvData
)
{...}
```

## Parameters

`hDot11SvcHandle`

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`hConnectSession`

The handle used by the operating system to reference the connection session with the BSS network.
     This handle value was specified through a previous call to the 
     <mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
     Dot11ExtIhvPerformPreAssociate</i></mshelp:link> IHV Handler function.

`dwSessionID`

The session identifier (session ID) of the current user.

`dwDataSize`

The size, in bytes, of the buffer referenced by 
     <i>pvData</i> .

`pvData`

A pointer to a caller-allocated buffer, which contains the data in a format defined by the
     IHV.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

The operating system will not encrypt the data referenced by the 
    <i>pvData</i> parameter before storing it within the system registry. The IHV Extensions DLL should use
    its own encryption algorithm to encrypt the data prior to calling 
    <b>Dot11ExtSetProfileCustomUserData</b>.

For every wireless WLAN profile used by the Native Wifi AutoConfig service, Windows maintains the
    concept of custom user data. This custom user data is initially non-existent, but can be set by calling
    the 
    <i>Dot11ExtSetProfileCustomUserData</i> function. The custom user data gets reset to empty any time the
    profile is modified by calling the 
    <mshelp:link keywords="netvista.dot11extsetcurrentprofile" tabindex="0"><b>
    Dot11ExtSetCurrentProfile</b></mshelp:link> function.

After custom user data has been set, this data can be accessed using the 
    <mshelp:link keywords="netvista.dot11extgetprofilecustomuserdata" tabindex="0"><b>
    Dot11ExtGetProfileCustomUserData</b></mshelp:link> function. The operating system stores the data under the system
    registry HKEY_CURRENT_USER key for the user that is referenced by the handle passed in the 
    <i>dwSessionID</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<mshelp:link keywords="netvista.dot11extgetprofilecustomuserdata" tabindex="0"><b>
   Dot11ExtGetProfileCustomUserData</b></mshelp:link>

<mshelp:link keywords="netvista.dot11extihvperformpreassociate" tabindex="0"><i>
   Dot11ExtIhvPerformPreAssociate</i></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>