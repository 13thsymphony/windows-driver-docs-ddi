---
UID: NS:ks.KSPROPERTY_ITEM
title: KSPROPERTY_ITEM
author: windows-driver-content
description: Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set.
old-location: stream\ksproperty_item.htm
old-project: stream
ms.assetid: 58530a72-6e07-44f5-9d7d-04bc37ff1ec9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_ITEM, KSPROPERTY_ITEM, KSPROPERTY_ITEM structure [Streaming Media Devices], PKSPROPERTY_ITEM, PKSPROPERTY_ITEM structure pointer [Streaming Media Devices], ks-struct_ae02482e-27d1-4485-8fe2-3b9a7393c683.xml, ks/KSPROPERTY_ITEM, ks/PKSPROPERTY_ITEM, stream.ksproperty_item"
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
-	KSPROPERTY_ITEM
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_ITEM, *PKSPROPERTY_ITEM
---

# KSPROPERTY_ITEM structure
Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set.

## Syntax
```
typedef struct KSPROPERTY_ITEM {
  ULONG                   PropertyId;
  union {
    PFNKSHANDLER GetPropertyHandler;
    BOOLEAN      GetSupported;
  };
  ULONG                   MinProperty;
  ULONG                   MinData;
  union {
    PFNKSHANDLER SetPropertyHandler;
    BOOLEAN      SetSupported;
  };
  const KSPROPERTY_VALUES *Values;
  ULONG                   RelationsCount;
  const KSPROPERTY        *Relations;
  PFNKSHANDLER            SupportHandler;
  ULONG                   SerializedSize;
}  *PKSPROPERTY_ITEM;
```

## Members


`PropertyId`

Specifies the ID of the property being described.

`MinProperty`

Specifies the minimum buffer length to hold the property identifier. This must be at least <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>).

`MinData`

Specifies the minimum buffer length to hold the data read from or written to this property.

`Values`

Pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff565966">KSPROPERTY_VALUES</a>. Specifies the acceptable and/or default values for the property. These are the same as the values reported by a driver in response to an IOCTL_KS_PROPERTY request with the KSPROPERTY_TYPE_BASICSUPPORT and KSPROPERTY_TYPE_DEFAULTVALUES flags set.

`RelationsCount`

Specifies the number of entries in the array pointed to by the <b>Relations</b> member.

`Relations`

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structures representing properties related to this one. Two properties are considered related if changing one property may affect the value of the other property. The <b>Flags</b> member of each entry is unused.

`SupportHandler`

Provide this member only if implementing your own format for raw serialization or raw unserialization. Basic support queries, range queries, and relations queries are automatically handled by AVStream, which returns the relevant values from other members of this KSPROPERTY_ITEM structure.

`SerializedSize`

Specifies the size of the property when serialized in a KSPROPERTY_TYPE_SERIALIZESET request. This should be zero if the property cannot be serialized. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> for more information.

## Remarks
Stream class minidrivers use KSPROPERTY_ITEM to describe to the client how to fulfill property requests on each property within a set. Handling for the property set as a whole is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a> structure, which contains pointers to arrays of KSPROPERTY_ITEM structures.

The stream class driver handles property requests on behalf of the minidriver. When the stream class driver requires more information from the minidriver, it passes an SRB_XXX request to one of the minidriver's <b>StrMiniReceiveXXXRequest</b> routines. The stream class driver handles the different request types as listed in the following table.

<table>
<tr>
<th>Property request flags value</th>
<th>Response</th>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_GET

</td>
<td>
If <b>GetSupported</b> is <b>TRUE</b>, the stream class driver submits an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568170">SRB_GET_DEVICE_PROPERTY</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff568175">SRB_GET_STREAM_PROPERTY</a> request to the appropriate minidriver <b>StrMiniReceiveXXXRequest</b> routine.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SET

</td>
<td>
If <b>SetSupported</b> is <b>TRUE</b>, the stream class driver submits an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568204">SRB_SET_DEVICE_PROPERTY</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff568207">SRB_SET_STREAM_PROPERTY</a> request to the appropriate minidriver <b>StrMiniReceiveXXXRequest</b> routine.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_BASICSUPPORT

</td>
<td>
The stream class driver uses KSPROPERTY_ITEM to obtain the information necessary to fulfill this request. For example, to specify the data type and permitted ranges of the property data, they each use the <b>Values</b> member of this structure.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_SETSUPPORT

</td>
<td>
The stream class driver completes the property request IRP as STATUS_SUCCESS only if the driver supplies an entry for the property set within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a> structure.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_DEFAULTVALUES

</td>
<td>
The stream class driver uses the <b>Values</b> member of this structure to determine the default values for the property data.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TYPE_RELATIONS

</td>
<td>
The stream class driver uses the <b>Relations</b> member to determine what properties are related to this property.

</td>
</tr>
</table>
 

If the client specifies KSPROPERTY_TYPE_DEFAULTVALUES, the driver uses the data buffer to return a description of its value type, including possibly its allowed range and default value. This flag is similar in result to KSPROPERTY_TYPE_BASICSUPPORT, except that any values returned are those that have been marked with KSPROPERTY_MEMBER_FLAG_DEFAULT in the <b>Flags</b> member of the structure <a href="https://msdn.microsoft.com/library/windows/hardware/ff565189">KSPROPERTY_MEMBERSHEADER</a>.

For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565966">KSPROPERTY_VALUES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568170">SRB_GET_DEVICE_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568175">SRB_GET_STREAM_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568204">SRB_SET_DEVICE_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568207">SRB_SET_STREAM_PROPERTY</a>