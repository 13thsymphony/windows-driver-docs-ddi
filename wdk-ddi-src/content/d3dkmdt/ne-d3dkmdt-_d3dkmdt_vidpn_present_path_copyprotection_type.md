---
UID: NE.d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE
title: _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration is used to indicate the type of copy protection that is supported by a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection_type.htm
old-project: display
ms.assetid: ee9405a6-7d56-4ca6-98c2-fd04addef8cd
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE
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
req.irql: PASSIVE_LEVEL
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration



## -description
The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration is used to indicate the type of copy protection that is supported by a VidPN present path.



## -syntax

````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE { 
  D3DKMDT_VPPMT_UNINITIALIZED            = 0,
  D3DKMDT_VPPMT_NOPROTECTION             = 1,
  D3DKMDT_VPPMT_MACROVISION_APSTRIGGER   = 2,
  D3DKMDT_VPPMT_MACROVISION_FULLSUPPORT  = 3
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE;
````


## -enum-fields

### -field D3DKMDT_VPPMT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPMT_NOPROTECTION

Indicates that the path has no copy protection.


### -field D3DKMDT_VPPMT_MACROVISION_APSTRIGGER

Indicates that the path provides support for Rovi's (formerly Macrovision) analog protection system (APS).


### -field D3DKMDT_VPPMT_MACROVISION_FULLSUPPORT

Indicates that the path provides full Rovi (formerly Macrovision) copy protection support.


## -remarks
The <b>CopyProtectionType</b> member of the <a href="display.d3dkmdt_vidpn_present_path_copyprotection">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION</a> structure is a value from the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enumeration.


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