---
UID: NE.d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
title: _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
author: windows-driver-content
description: The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).
old-location: display\displayid_detailed_timing_type_i_sync_polarity.htm
old-project: display
ms.assetid: 6563d4f7-3750-49c1-80f5-14a839e70cb7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY,
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
req.alt-api: _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY
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

# _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration



## -description
The DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY enumeration indicates the display device's sync polarity (whether the sync signal is positive or negative).



## -syntax

````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY {
  DIDDT1_Sync_Positive  = 0, 
  DIDDT1_Sync_Negative  = 1 

};
````


## -enum-fields

### -field DIDDT1_Sync_Positive

Indicates that the sync polarity is positive.


### -field DIDDT1_Sync_Negative

Indicates that the sync polarity is negative.


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