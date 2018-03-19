---
UID: NS:ks.KSPROPERTY_MEMBERSHEADER
title: KSPROPERTY_MEMBERSHEADER
author: windows-driver-content
description: A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.
old-location: stream\ksproperty_membersheader.htm
old-project: stream
ms.assetid: 8a5d8f8c-4924-4ae0-a7b2-8d2b04a49a9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER structure [Streaming Media Devices], PKSPROPERTY_MEMBERSHEADER, PKSPROPERTY_MEMBERSHEADER structure pointer [Streaming Media Devices], ks-struct_d43fb5ec-043b-4378-8bdb-aaf80a616150.xml, ks/KSPROPERTY_MEMBERSHEADER, ks/PKSPROPERTY_MEMBERSHEADER, stream.ksproperty_membersheader"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSPROPERTY_MEMBERSHEADER
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_MEMBERSHEADER, *PKSPROPERTY_MEMBERSHEADER
---

# KSPROPERTY_MEMBERSHEADER structure
A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.

## Syntax
````
typedef struct {
  ULONG MembersFlags;
  ULONG MembersSize;
  ULONG MembersCount;
  ULONG Flags;
} KSPROPERTY_MEMBERSHEADER, *PKSPROPERTY_MEMBERSHEADER;
````

## Members


`MembersFlags`

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the <b>PropTypeSet</b> member of the <a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a> structure. The number of range pairs is determined by <b>MembersCount</b>. This should be one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_RANGES

</td>
<td>
Indicates that list members are ranges, of type <a href="..\ks\ns-ks-ksproperty_bounds_long.md">KSPROPERTY_BOUNDS_LONG</a> or <a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>.

</td>
</tr>
<tr>
<td>

<dl>
<dt>KSPROPERTY_MEMBER</dt>
<dt>_STEPPEDRANGES</dt>
</dl>


</td>
<td>
Indicates that the following members are stepped values within ranges, of type <a href="..\ks\ns-ks-ksproperty_stepping_long.md">KSPROPERTY_STEPPING_LONG</a> or <a href="..\ks\ns-ks-ksproperty_stepping_longlong.md">KSPROPERTY_STEPPING_LONGLONG</a>..

</td>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_VALUES

</td>
<td>
Each entry in the members array is a single value.

</td>
</tr>
</table>

`MembersSize`

Specifies the size, in bytes, of an individual array element.

`MembersCount`

Specifies the number of entries in the members array.

`Flags`

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the <b>PropTypeSet</b> member of the <a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a> structure. The number of range pairs is determined by <b>MembersCount</b>. This should be one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_RANGES

</td>
<td>
Indicates that list members are ranges, of type <a href="..\ks\ns-ks-ksproperty_bounds_long.md">KSPROPERTY_BOUNDS_LONG</a> or <a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>.

</td>
</tr>
<tr>
<td>

<dl>
<dt>KSPROPERTY_MEMBER</dt>
<dt>_STEPPEDRANGES</dt>
</dl>


</td>
<td>
Indicates that the following members are stepped values within ranges, of type <a href="..\ks\ns-ks-ksproperty_stepping_long.md">KSPROPERTY_STEPPING_LONG</a> or <a href="..\ks\ns-ks-ksproperty_stepping_longlong.md">KSPROPERTY_STEPPING_LONGLONG</a>..

</td>
</tr>
<tr>
<td>
KSPROPERTY_MEMBER_VALUES

</td>
<td>
Each entry in the members array is a single value.

</td>
</tr>
</table>

## Remarks
The size of the array can be determined by multiplying <b>MembersCount</b> by <b>MembersSize</b>.

A <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure contains a KSPROPERTY_MEMBERSHEADER structure as its first member. The second member, <b>Members</b>, points to an array of property values or ranges.

In addition, a <a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a> structure can be followed by a list of KSPROPERTY_MEMBERSHEADER structures.

For more information about KSPROPERTY_MEMBER_FLAG_DEFAULT, see <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>. For more information about KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_MULTICHANNEL and KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_UNIFORM, see <a href="https://msdn.microsoft.com/48ee3b33-fb97-4e71-bf6f-5dbdb76aa7f8">Exposing Multichannel Nodes</a> in the Windows Driver Kit (WDK) Audio documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a>



<a href="..\ks\ns-ks-ksproperty_stepping_long.md">KSPROPERTY_STEPPING_LONG</a>



<a href="..\ks\ns-ks-ksproperty_stepping_longlong.md">KSPROPERTY_STEPPING_LONGLONG</a>



<a href="..\ks\ns-ks-ksproperty_bounds_long.md">KSPROPERTY_BOUNDS_LONG</a>



<a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>



<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>



<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>