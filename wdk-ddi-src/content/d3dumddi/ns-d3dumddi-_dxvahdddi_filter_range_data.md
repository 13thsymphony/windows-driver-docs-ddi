---
UID: NS.D3DUMDDI._DXVAHDDDI_FILTER_RANGE_DATA
title: _DXVAHDDDI_FILTER_RANGE_DATA
author: windows-driver-content
description: Describes a filter range.
old-location: display\dxvahdddi_filter_range_data.htm
old-project: display
ms.assetid: 46f5ee68-ed1a-4da4-b761-60157efb3252
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_FILTER_RANGE_DATA, DXVAHDDDI_FILTER_RANGE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_FILTER_RANGE_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_FILTER_RANGE_DATA
req.alt-loc: d3dumddi.h
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

# _DXVAHDDDI_FILTER_RANGE_DATA structure



## -description
The <b>DXVAHDDDI_FILTER_RANGE_DATA</b> structure describes a filter range.



## -syntax

````
typedef struct _DXVAHDDDI_FILTER_RANGE_DATA {
  INT   Minimum;
  INT   Maximum;
  INT   Default;
  FLOAT Multiplier;
} DXVAHDDDI_FILTER_RANGE_DATA;
````


## -struct-fields

### -field Minimum


      [in] An <b>INT</b> that specifies the minimum value in the filter range. 
     


### -field Maximum

[in] An <b>INT</b> that specifies the maximum value in the filter range. 


### -field Default

[in] An <b>INT</b> that specifies the default value for the filter range. 


### -field Multiplier

[in] A <b>FLOAT</b> value that specifies a multiplier to calculate the actual filter value. 


## -remarks
A hue ProcAmp filter that is defined from –180.0 to 180.0 at 0.25 step size with a default value of 0.0 has the members of the <b>DXVAHDDDI_FILTER_RANGE_DATA</b> structure set to the following values, which are normalized by an implicit step size of 1:


     Minimum = –720


     Maximum = 720


     Default = 0


     Multiplier = 0.25


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
<b>DXVAHDDDI_FILTER_RANGE_DATA</b> is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>