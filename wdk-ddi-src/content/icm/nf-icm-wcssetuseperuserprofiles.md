---
UID : NF:icm.WcsSetUsePerUserProfiles
title : WcsSetUsePerUserProfiles function
author : windows-driver-content
description : The WcsSetUsePerUserProfiles function allows the user to specify whether or not to use a per-user profile association list for the specified device.
old-location : print\wcssetuseperuserprofiles.htm
old-project : print
ms.assetid : e14f944f-67fe-4eb8-85b2-9ba262e2e549
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : WcsSetUsePerUserProfiles
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : icm.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Included in Windows Vista and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WcsSetUsePerUserProfiles
req.alt-loc : Mscms.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Mscms.lib
req.dll : Mscms.dll
req.irql : 
req.typenames : WCS_PROFILE_MANAGEMENT_SCOPE
---


# WcsSetUsePerUserProfiles function
The <code>WcsSetUsePerUserProfiles</code> function allows the user to specify whether or not to use a per-user profile association list for the specified device.

## Syntax

````
BOOL WcsSetUsePerUserProfiles(
  _In_ LPCWSTR pDeviceName,
  _In_ DWORD   dwDeviceClass,
  _In_ BOOL    usePerUserProfiles
);
````

## Parameters

`pDeviceName`

A pointer to a string that contains the friendly name of the device.

`dwDeviceClass`

A flag value that specifies the class of the device. This parameter must take one of the following values:

`usePerUserProfiles`

A Boolean value that is <b>TRUE</b> if the user wants to use a per-user profile association list for the specified device; otherwise <b>FALSE</b>.


## Return Value

None

## Remarks

This function will fail if the device pointed to by <i>pDeviceName</i> is not of the class specified by <i>dwDeviceClass</i>.

This function is executable in Least-Privileged User Account (LUA) context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | icm.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\icm\nf-icm-wcsgetuseperuserprofiles.md">WcsGetUsePerUserProfiles</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsSetUsePerUserProfiles function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>