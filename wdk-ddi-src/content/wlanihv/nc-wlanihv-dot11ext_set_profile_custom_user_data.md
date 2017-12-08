---
UID: NC.wlanihv.DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
title: DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetprofilecustomuserdata.htm
old-project: netvista
ms.assetid: 25e1462c-6eaa-480a-9f9e-6f8689da05c5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BINARY_CONTAINER, BINARY_CONTAINER, *PBINARY_CONTAINER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtSetProfileCustomUserData
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
req.product: Windows 10 or later.
---

# DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetProfileCustomUserData(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_opt_ HANDLE hConnectSession,
  _In_     DWORD  dwSessionID,
  _In_     DWORD  dwDataSize,
  _In_     LPVOID pvData
);
````


## -parameters

### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param hConnectSession [in, optional]

The handle used by the operating system to reference the connection session with the BSS network.
     This handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.

### -param dwSessionID [in]

The session identifier (session ID) of the current user.

### -param dwDataSize [in]

The size, in bytes, of the buffer referenced by 
     <i>pvData</i> .

### -param pvData [in]

A pointer to a caller-allocated buffer, which contains the data in a format defined by the
     IHV.

## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## -remarks
The operating system will not encrypt the data referenced by the 
    <i>pvData</i> parameter before storing it within the system registry. The IHV Extensions DLL should use
    its own encryption algorithm to encrypt the data prior to calling 
    <b>Dot11ExtSetProfileCustomUserData</b>.

For every wireless WLAN profile used by the Native Wifi AutoConfig service, Windows maintains the
    concept of custom user data. This custom user data is initially non-existent, but can be set by calling
    the 
    <i>Dot11ExtSetProfileCustomUserData</i> function. The custom user data gets reset to empty any time the
    profile is modified by calling the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">
    Dot11ExtSetCurrentProfile</a> function.

After custom user data has been set, this data can be accessed using the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">
    Dot11ExtGetProfileCustomUserData</a> function. The operating system stores the data under the system
    registry HKEY_CURRENT_USER key for the user that is referenced by the handle passed in the 
    <i>dwSessionID</i> parameter.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="..\wlanihv\nc-wlanihv-dot11ext_get_profile_custom_user_data.md">
   Dot11ExtGetProfileCustomUserData</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_set_current_profile.md">Dot11ExtSetCurrentProfile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_PROFILE_CUSTOM_USER_DATA callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
