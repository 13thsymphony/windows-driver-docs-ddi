---
UID: NE.d3d10umddi.D3D10_DDI_PRIMITIVE_TOPOLOGY
title: D3D10_DDI_PRIMITIVE_TOPOLOGY
author: windows-driver-content
description: The D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration type contains values that identify primitive topologies in a call to the driver's IaSetTopology function.
old-location: display\d3d10_ddi_primitive_topology.htm
old-project: display
ms.assetid: 49e7f8d3-36e2-41d6-9cea-ea0c284586e6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D10_DDI_PRIMITIVE_TOPOLOGY, D3D10_DDI_PRIMITIVE_TOPOLOGY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10_DDI_PRIMITIVE_TOPOLOGY
req.alt-loc: d3d10umddi.h
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

# D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration



## -description
The D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration type contains values that identify primitive topologies in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md">IaSetTopology</a> function.



## -syntax

````
typedef enum D3D10_DDI_PRIMITIVE_TOPOLOGY { 
  D3D10_DDI_PRIMITIVE_TOPOLOGY_UNDEFINED                   = 0,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_POINTLIST                   = 1,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST                    = 2,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP                   = 3,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST                = 4,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP               = 5,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST_ADJ                = 10,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP_ADJ               = 11,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST_ADJ            = 12,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP_ADJ           = 13,
#if D3D11DDI_MINOR_HEADER_VERSION >= 1
  D3D11_DDI_PRIMITIVE_TOPOLOGY_1_CONTROL_POINT_PATCHLIST   = 33,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_2_CONTROL_POINT_PATCHLIST   = 34,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_3_CONTROL_POINT_PATCHLIST   = 35,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_4_CONTROL_POINT_PATCHLIST   = 36,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_5_CONTROL_POINT_PATCHLIST   = 37,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_6_CONTROL_POINT_PATCHLIST   = 38,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_7_CONTROL_POINT_PATCHLIST   = 39,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_8_CONTROL_POINT_PATCHLIST   = 40,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_9_CONTROL_POINT_PATCHLIST   = 41,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_10_CONTROL_POINT_PATCHLIST  = 42,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_11_CONTROL_POINT_PATCHLIST  = 43,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_12_CONTROL_POINT_PATCHLIST  = 44,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_13_CONTROL_POINT_PATCHLIST  = 45,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_14_CONTROL_POINT_PATCHLIST  = 46,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_15_CONTROL_POINT_PATCHLIST  = 47,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_16_CONTROL_POINT_PATCHLIST  = 48,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_17_CONTROL_POINT_PATCHLIST  = 49,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_18_CONTROL_POINT_PATCHLIST  = 50,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_19_CONTROL_POINT_PATCHLIST  = 51,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_20_CONTROL_POINT_PATCHLIST  = 52,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_21_CONTROL_POINT_PATCHLIST  = 53,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_22_CONTROL_POINT_PATCHLIST  = 54,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_23_CONTROL_POINT_PATCHLIST  = 55,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_24_CONTROL_POINT_PATCHLIST  = 56,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_25_CONTROL_POINT_PATCHLIST  = 57,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_26_CONTROL_POINT_PATCHLIST  = 58,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_27_CONTROL_POINT_PATCHLIST  = 59,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_28_CONTROL_POINT_PATCHLIST  = 60,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_29_CONTROL_POINT_PATCHLIST  = 61,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_30_CONTROL_POINT_PATCHLIST  = 62,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_31_CONTROL_POINT_PATCHLIST  = 63,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_32_CONTROL_POINT_PATCHLIST  = 64

#endif } D3D10_DDI_PRIMITIVE_TOPOLOGY;
````


## -enum-fields

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_UNDEFINED

The primitive topology is undefined.


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_POINTLIST

Vertices are rendered as a collection of isolated points.


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST

Vertices are rendered as a list of isolated straight line segments.


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP

Vertices are rendered as a single polyline.


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST


      Vertices are rendered as a sequence of isolated triangles. Each group of three vertices defines a separate triangle.
     


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP

Vertices are rendered as a triangle strip. 


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST_ADJ

The primitives contain room for adjacency information.  


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP_ADJ

The primitives contain room for adjacency information. 


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST_ADJ

The primitives contain room for adjacency information. 


### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP_ADJ

The primitives contain room for adjacency information. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_1_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_2_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions.


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_3_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions.


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_4_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions.


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_5_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions.


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_6_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_7_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_8_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_9_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_10_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_11_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_12_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_13_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_14_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_15_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_16_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_17_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_18_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_19_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_20_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_21_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_22_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_23_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_24_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_25_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_26_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_27_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_28_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_29_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_30_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_31_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_32_CONTROL_POINT_PATCHLIST

Supported in Windows 7 and later versions. 


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md">IaSetTopology</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

