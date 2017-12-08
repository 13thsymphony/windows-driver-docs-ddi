---
UID: NF.icm.WcsSetDefaultColorProfile
title: WcsSetDefaultColorProfile function
author: windows-driver-content
description: The WcsSetDefaultColorProfile function sets the default color profile name of the specified profile type in the specified profile management scope.
old-location: print\wcssetdefaultcolorprofile.htm
old-project: print
ms.assetid: 302f271c-801e-409c-a0fc-53f01e5e2055
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: WcsSetDefaultColorProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Included in Windows Vista and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WcsSetDefaultColorProfile
req.alt-loc: Mscms.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
---

# WcsSetDefaultColorProfile function



## -description
The <code>WcsSetDefaultColorProfile</code> function sets the default color profile name of the specified profile type in the specified profile management scope.


## -syntax

````
BOOL WcsSetDefaultColorProfile(
  _In_     WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_opt_ PCWSTR                       pDeviceName,
  _In_     COLORPROFILETYPE             cptColorProfileType,
  _In_     COLORPROFILESUBTYPE          cpstColorProfileSubType,
  _In_     DWORD                        dwProfileID,
  _In_opt_ LPCWSTR                      pProfileName
);
````


## -parameters

### -param profileManagementScope [in]


      A <a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a> value that specifies the scope of this profile management operation.

### -param pDeviceName [in, optional]

A pointer to the name of the device for which the default color profile is to be set. If <b>NULL</b>, a device-independent default profile will be used.

### -param cptColorProfileType [in]

A <a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a> value that specifies the color profile type.

### -param cpstColorProfileSubType [in]

A <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.

### -param dwProfileID [in]

The ID of the color space that the color profile represents.

### -param pProfileName [in, optional]

A pointer to a buffer to receive the name of the color profile. See Remarks.

## -remarks
If the <i>pProfileName</i> parameter is <b>NULL</b> and the <i>profileManagementScope</i> parameter is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, subsequent calls to <b>WcsSetDefaultColorProfile</b> will return the system-wide default profile.

This function is executable in Least-Privileged User Account (LUA) context if <i>profileManagementScope</i> is WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER. Otherwise, administrative privileges are required. The specified profile must already be installed, but it need not yet be associated with the specified device in the specified profile management scope..

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Included in Windows Vista and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Icm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Mscms.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Mscms.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a>
</dt>
<dt>
<a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a>
</dt>
<dt>
<a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a>
</dt>
<dt>
<a href="print.wcsgetdefaultcolorprofilesize">WcsGetDefaultColorProfileSize</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsSetDefaultColorProfile function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
