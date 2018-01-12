---
UID: NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE
title: _DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE enumeration indicates the display device's frame scanning mode.
old-location: display\displayid_detailed_timing_type_i_scanning_mode.htm
old-project: display
ms.assetid: 8a5d3fba-ffd5-4fbc-973a-d5bfec6bb6e3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE
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
req.typenames: 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE enumeration



## -description
The DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE enumeration indicates the display device's frame scanning mode.



## -syntax

````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE {
  DIDDT1_Progressive  = 0, 
  DIDDT1_Interlaced   = 1 

};
````


## -enum-fields

### -field DIDDT1_Progressive

Indicates a progressive scanning mode.


### -field DIDDT1_Interlaced

Indicates an interlaced scanning mode.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating systems.

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