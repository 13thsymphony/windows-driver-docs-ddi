---
UID: NC.wlanihv.DOT11EXTIHV_VALIDATE_PROFILE
title: DOT11EXTIHV_VALIDATE_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvvalidateprofile.htm
old-project: netvista
ms.assetid: 724a6c17-e020-44e1-9d00-332daa5dbdfb
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PrintPropertyValue, PrintPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvValidateProfile
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

# DOT11EXTIHV_VALIDATE_PROFILE callback



## -description

## -prototype

````
DOT11EXTIHV_VALIDATE_PROFILE Dot11ExtIhvValidateProfile;

DWORD APIENTRY Dot11ExtIhvValidateProfile(
  _In_opt_ HANDLE                             hIhvExtAdapter,
  _In_opt_ PDOT11EXT_IHV_PROFILE_PARAMS       pIhvProfileParams,
  _In_     PDOT11EXT_IHV_CONNECTIVITY_PROFILE pIhvConnProfile,
  _In_     PDOT11EXT_IHV_SECURITY_PROFILE     pIhvSecProfile,
  _Out_    PDWORD                             pdwReasonCode
)
{ ... }
````


## -parameters
<dl>

### -param hIhvExtAdapter [in, optional]

<dd>
<p>The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.</p>
</dd>

### -param pIhvProfileParams [in, optional]

<dd>
<p>A pointer to a 
     <a href="..\wlanihvtypes\ns-wlanihvtypes--dot11ext-ihv-profile-params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure. This structure defines the attributes of the basic service
     set (BSS) network to which the profile extensions will be applied.</p>
</dd>

### -param pIhvConnProfile [in]

<dd>
<p>A pointer to a 
     <a href="..\wlanihv\ns-wlanihv--dot11ext-ihv-connectivity-profile.md">
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</a> structure that contains connectivity settings for the IHV
     profile.</p>
</dd>

### -param pIhvSecProfile [in]

<dd>
<p>A pointer to a 
     <a href="..\wlanihv\ns-wlanihv--dot11ext-ihv-security-profile.md">
     DOT11EXT_IHV_SECURITY_PROFILE</a> structure that contains security settings for the IHV
     profile.</p>
</dd>

### -param pdwReasonCode [out]

<dd>
<p>A pointer to a DWORD value, which provides additional information for the return value of the 
     <i>Dot11ExtIhvValidateProfile</i> function. The IHV Extensions DLL must set *
     <i>pdwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in 
     L2cmn.h.</p>
</dd>
</dl>

## -returns
<p>If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.</p>

## -remarks
<p>The operating system calls the 
    <i>Dot11ExtIhvValidateProfile</i> function to verify the user-specified settings for a network profile
    before the profile is processed or saved.</p>

<p>When the 
    <i>Dot11ExtIhvValidateProfile</i> function is called, the IHV Extensions DLL follows these guidelines:</p>

<p>The IHV Extensions DLL verifies that the user-specified profile settings are valid for the general
      attributes of the basic service set (BSS) network to which the profile will be applied. The BSS network
      attributes are referenced through the 
      <i>pIhvProfileParams</i> parameter.</p>

<p>If the user data is valid for the network profile extensions, 
      <i>Dot11ExtIhvValidateProfile</i> must return ERROR_SUCCESS. Otherwise, the function must return an
      appropriate error code from the ERROR_xxxx values defined in 
      Winerror.h.</p>

<p>The IHV Extensions DLL provides more information regarding the results of the validation of the user
      data. The DLL must set *
      <i>pdwReasonCode</i> to one of the following:</p>

<p>L2_REASON_CODE_SUCCESS, if the user data is valid.</p>

<p>An appropriate L2_REASON_CODE_xxxx error value, if the user data is not valid.</p>

<p>An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1), regardless of the validity of the user data.</p>

<p>For more information about the Native 802.11 XML schema, refer to the Microsoft Windows SDK
    documentation.</p>

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
<dt>Wlanihv.h (include Wlanihv.h or L2cmn.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv--dot11ext-ihv-connectivity-profile.md">
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</a>
</dt>
<dt>
<a href="..\wlanihvtypes\ns-wlanihvtypes--dot11ext-ihv-profile-params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="..\wlanihv\ns-wlanihv--dot11ext-ihv-security-profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv-init-adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_VALIDATE_PROFILE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
