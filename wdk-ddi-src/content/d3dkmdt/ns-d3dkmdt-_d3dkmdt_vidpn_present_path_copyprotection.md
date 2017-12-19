---
UID: NS.D3DKMDT._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
title: _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection.htm
old-project: display
ms.assetid: 661e70c6-d99e-4c5a-ad88-3dd854747de4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
req.alt-loc: d3dkmdt.h
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
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure



## -description
The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.



## -syntax

````
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION {
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  BYTE                                              OEMCopyProtection[D3DKMDT_MACROVISION_OEMCOPYPROTECTION_SIZE];
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION;
````


## -struct-fields

### -field CopyProtectionType

A value from the <a href="display.d3dkmdt_vidpn_present_path_copyprotection_type">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE</a> enumeration that indicates the type of copy protection that is active on the path.


### -field APSTriggerBits

A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.


### -field OEMCopyProtection

Reserved for future use.


### -field CopyProtectionSupport

A <a href="display.d3dkmdt_vidpn_present_path_copyprotection_support">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT</a> structure that indicates the types of copy protection that are supported by the path.


## -remarks
The <b>CopyProtection</b> member of the  <a href="display.d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>