---
UID: NE.d3dkmdt._D3DKMDT_MONITOR_ORIENTATION
title: _D3DKMDT_MONITOR_ORIENTATION
author: windows-driver-content
description: The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.
old-location: display\d3dkmdt_monitor_orientation.htm
old-project: display
ms.assetid: 16e7d91c-04de-4a8c-97c2-c500d0d3697d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMDT_MONITOR_ORIENTATION, D3DKMDT_MONITOR_ORIENTATION
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
req.alt-api: D3DKMDT_MONITOR_ORIENTATION
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

# _D3DKMDT_MONITOR_ORIENTATION enumeration



## -description
The D3DKMDT_MONITOR_ORIENTATION enumeration is used to describe the orientation (rotation angle) of a connected external display device.



## -syntax

````
typedef enum _D3DKMDT_MONITOR_ORIENTATION { 
  D3DKMDT_MO_UNINITIALIZED  = 0,
  D3DKMDT_MO_0DEG           = 1,
  D3DKMDT_MO_90DEG          = 2,
  D3DKMDT_MO_180DEG         = 3,
  D3DKMDT_MO_270DEG         = 4
} D3DKMDT_MONITOR_ORIENTATION;
````


## -enum-fields

### -field D3DKMDT_MO_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_ORIENTATION has not yet been assigned a meaningful value.


### -field D3DKMDT_MO_0DEG

Indicates that the display device has not been rotated from its default orientation.


### -field D3DKMDT_MO_90DEG

Indicates that the display device has been rotated 90 degrees clockwise from its default orientation.


### -field D3DKMDT_MO_180DEG

Indicates that the display device has been rotated 180 degrees clockwise from its default orientation.


### -field D3DKMDT_MO_270DEG

Indicates that the display device has been rotated 270 degrees clockwise from its default orientation.


## -remarks


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