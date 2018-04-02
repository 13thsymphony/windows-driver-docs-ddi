---
UID: NS:ksmedia._KS_DVDCOPY_REGION
title: "_KS_DVDCOPY_REGION"
author: windows-driver-content
description: The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.
old-location: stream\ks_dvdcopy_region.htm
old-project: stream
ms.assetid: 159a8dd0-6efa-4f2c-921c-c427e1cf59ec
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DVDCOPY_REGION, KS_DVDCOPY_REGION, KS_DVDCOPY_REGION structure [Streaming Media Devices], PKS_DVDCOPY_REGION, PKS_DVDCOPY_REGION structure pointer [Streaming Media Devices], _KS_DVDCOPY_REGION, dvdref_ff087f30-2337-4b0f-8ae1-8a42cacaa5ae.xml, ksmedia/KS_DVDCOPY_REGION, ksmedia/PKS_DVDCOPY_REGION, stream.ks_dvdcopy_region"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_DVDCOPY_REGION
product: Windows
targetos: Windows
req.typenames: KS_DVDCOPY_REGION, *PKS_DVDCOPY_REGION
---

# _KS_DVDCOPY_REGION structure
The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.

## Syntax
```
typedef struct _KS_DVDCOPY_REGION {
  UCHAR Reserved;
  UCHAR RegionData;
  UCHAR Reserved2[2];
} *PKS_DVDCOPY_REGION, KS_DVDCOPY_REGION;
```

## Members


`Reserved`

Reserved. Do not use.

`RegionData`

Specifies the region code for the nationality or language, as described in the following table:

<table>
<tr>
<th>Numeric Code</th>
<th>Description</th>
</tr>
<tr>
<td>
1

</td>
<td>
North America

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Japan, European Union, Middle East, Egypt, South Africa and Greenland

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Southeast Asia (including Hong Kong SAR)

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Central/South America, Australia, New Zealand and the Caribbean

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Africa, Northwest Asia (including Korea)

</td>
</tr>
<tr>
<td>
6

</td>
<td>
China

</td>
</tr>
</table>

`Reserved2`

Reserved. Do not use.

## Remarks
The KS_DVDCOPY_REGION structure is used by the KSPROPERTY_DVDCOPY_REGION property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a> and <a href="https://msdn.microsoft.com/931441c8-9521-43c9-86f1-dbf75d36e190">DVD Regionalization</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565146">KSPROPERTY_DVDCOPY_REGION</a>