---
UID : NS:ks.KSPROPERTY_MEMBERSHEADER
title : KSPROPERTY_MEMBERSHEADER
author : windows-driver-content
description : A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.
old-location : stream\ksproperty_membersheader.htm
old-project : stream
ms.assetid : 8a5d8f8c-4924-4ae0-a7b2-8d2b04a49a9e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_MEMBERSHEADER, *PKSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_MEMBERSHEADER
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PKSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER"
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
        
            `MembersCount`

            Specifies the number of entries in the members array.
        
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
        
            `MembersSize`

            Specifies the size, in bytes, of an individual array element.

    ## Remarks
        The size of the array can be determined by multiplying <b>MembersCount</b> by <b>MembersSize</b>.

A <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure contains a KSPROPERTY_MEMBERSHEADER structure as its first member. The second member, <b>Members</b>, points to an array of property values or ranges.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_bounds_long.md">KSPROPERTY_BOUNDS_LONG</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_stepping_long.md">KSPROPERTY_STEPPING_LONG</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_stepping_longlong.md">KSPROPERTY_STEPPING_LONGLONG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_MEMBERSHEADER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>