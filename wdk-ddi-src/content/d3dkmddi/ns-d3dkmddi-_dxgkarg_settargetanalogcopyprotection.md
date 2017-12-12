---
UID: NS.D3DKMDDI._DXGKARG_SETTARGETANALOGCOPYPROTECTION
title: _DXGKARG_SETTARGETANALOGCOPYPROTECTION
author: windows-driver-content
description: Holds information to set analog copy protection on a display adapter's video present target.
old-location: display\dxgkarg_settargetanalogcopyprotection.htm
old-project: display
ms.assetid: F5A853B2-4A8C-4929-AAEC-28844DEF0B29
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_SETTARGETANALOGCOPYPROTECTION, DXGKARG_SETTARGETANALOGCOPYPROTECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_SETTARGETANALOGCOPYPROTECTION
req.alt-loc: d3dkmddi.h
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

# _DXGKARG_SETTARGETANALOGCOPYPROTECTION structure



## -description
Holds information to set analog copy protection on a display adapter's video present target.



## -syntax

````
typedef struct _DXGKARG_SETTARGETANALOGCOPYPROTECTION {
  D3DDDI_VIDEO_PRESENT_TARGET_ID                    TargetId;
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} DXGKARG_SETTARGETANALOGCOPYPROTECTION;
````


## -struct-fields

### -field TargetId

[in] The identifier of a display adapter's video present target.


### -field CopyProtectionType

[in] A value from the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE enum indicating the type of analog copy protection being requested.


### -field APSTriggerBits

[in] A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.


### -field CopyProtectionSupport

[in] A D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure containing flags indicating the analog copy protection support being requested.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>