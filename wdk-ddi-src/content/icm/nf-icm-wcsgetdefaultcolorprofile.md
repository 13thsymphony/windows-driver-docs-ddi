---
UID: NF:icm.WcsGetDefaultColorProfile
title: WcsGetDefaultColorProfile function
author: windows-driver-content
description: The WcsGetDefaultColorProfile function retrieves the default color profile for a device, or the device-independent default if the device is not specified.
old-location: print\wcsgetdefaultcolorprofile.htm
old-project: print
ms.assetid: a5ace7f3-dc61-4799-b129-3c25c392ebf6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WcsGetDefaultColorProfile, WcsGetDefaultColorProfile function [Print Devices], colorfnc_c7de4cff-ebfb-4392-a2a2-1229a6b08aa1.xml, icm/WcsGetDefaultColorProfile, print.wcsgetdefaultcolorprofile
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Mscms.dll
api_name:
-	WcsGetDefaultColorProfile
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---


# WcsGetDefaultColorProfile function
The <code>WcsGetDefaultColorProfile</code> function retrieves the default color profile for a device, or the device-independent default if the device is not specified.

## Syntax

````
BOOL WcsGetDefaultColorProfile(
  _In_     WCS_PROFILE_MANAGEMENT_SCOPE profileManagementScope,
  _In_opt_ PCWSTR                       pDeviceName,
  _In_     COLORPROFILETYPE             cptColorProfileType,
  _In_     COLORPROFILESUBTYPE          cpstColorProfileSubType,
  _In_     DWORD                        dwProfileID,
  _In_     DWORD                        cbProfileName,
  _Out_    LPWSTR                       pProfileName
);
````

## Parameters

`scope`

TBD

`pDeviceName`

A pointer to the name of the device for which the default color profile is to be obtained. If <b>NULL</b>, a device-independent default profile will be obtained.

`cptColorProfileType`

A <a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a> value that specifies the color profile type.

`cpstColorProfileSubType`

A <a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a> value that specifies the color profile subtype.

`dwProfileID`

The ID of the color space that the color profile represents.

`cbProfileName`

The buffer size, in bytes, of the buffer pointed to by <i>pProfileName</i>.

`pProfileName`

A pointer to a buffer to receive the name of the color profile.


## Return Value

None

## Remarks

Use the <a href="..\icm\nf-icm-wcsgetdefaultcolorprofilesize.md">WcsGetDefaultColorProfileSize</a> function to obtain the required size of the buffer pointed to by the <i>pProfileName</i> parameter.

If WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, the current user setting, is present, it overrides the system-wide default for <i>profileManagementScope</i>.

This function is executable in Least-Privileged User Account (LUA) context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Included in Windows Vista and later.  |
| **Target Platform** | Universal |
| **Header** | icm.h |
| **Library** | Mscms.lib |
| **DLL** | Mscms.dll |

## See Also

<a href="..\icm\ne-icm-colorprofilesubtype.md">COLORPROFILESUBTYPE</a>



<a href="..\icm\ne-icm-colorprofiletype.md">COLORPROFILETYPE</a>



<a href="..\icm\ne-icm-wcs_profile_management_scope.md">WCS_PROFILE_MANAGEMENT_SCOPE</a>



<a href="..\icm\nf-icm-wcsgetdefaultcolorprofilesize.md">WcsGetDefaultColorProfileSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsGetDefaultColorProfile function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>