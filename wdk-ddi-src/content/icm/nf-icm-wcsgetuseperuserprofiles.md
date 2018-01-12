---
UID: NF:icm.WcsGetUsePerUserProfiles
title: WcsGetUsePerUserProfiles function
author: windows-driver-content
description: The WcsGetUsePerUserProfiles function determines whether the user has chosen to use a per-user profile association list for the specified device.
old-location: print\wcsgetuseperuserprofiles.htm
old-project: print
ms.assetid: 6a970bec-c773-498e-b93a-2bd9f625e194
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: WcsGetUsePerUserProfiles
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
req.alt-api: WcsGetUsePerUserProfiles
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
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsGetUsePerUserProfiles function



## -description
The <code>WcsGetUsePerUserProfiles</code> function determines whether the user has chosen to use a per-user profile association list for the specified device.



## -syntax

````
BOOL WcsGetUsePerUserProfiles(
  _In_  LPCWSTR pDeviceName,
  _In_  DWORD   dwDeviceClass,
  _Out_ PBOOL   pUsePerUserProfiles
);
````


## -parameters

### -param pDeviceName [in]

A pointer to a string that contains the friendly name of the device.


### -param dwDeviceClass [in]

A flag value that specifies the class of the device. This parameter must take one of the following values:




### -param CLASS_MONITOR

Specifies a display device.


### -param CLASS_PRINTER

Specifies a printer.


### -param CLASS_SCANNER

Specifies an image capture device.

</dd>
</dl>

### -param pUsePerUserProfiles [out]

A pointer to a location to receive a Boolean value that is <b>TRUE</b> if the user has chosen to use a per-user profile association list for the specified device; otherwise <b>FALSE</b>.


## -remarks
This function will fail if the device pointed to by <i>pDeviceName</i> is not of the class specified by <i>dwDeviceClass</i>.

This function is executable in Least-Privileged User Account (LUA) context.


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
<a href="..\icm\nf-icm-wcssetuseperuserprofiles.md">WcsSetUsePerUserProfiles</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsGetUsePerUserProfiles function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

