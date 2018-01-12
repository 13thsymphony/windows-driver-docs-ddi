---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO
title: _NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure contains information about a Hyper-V extensible switch port policy property.
old-location: netvista\ndis_switch_port_property_enum_info.htm
old-project: netvista
ms.assetid: 537342c3-fbcf-493d-98ce-64ea1a84225b
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO, NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO, *PNDIS_SWITCH_PORT_PROPERTY_ENUM_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO
req.alt-loc: Ntddndis.h
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
req.typenames: NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO, *PNDIS_SWITCH_PORT_PROPERTY_ENUM_INFO
---

# _NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure



## -description
The <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure contains information about a Hyper-V extensible switch port policy property.



## -syntax

````
typedef struct _NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_SWITCH_OBJECT_VERSION     PropertyVersion;
  NDIS_SWITCH_OBJECT_INSTANCE_ID PropertyInstanceId;
  ULONG                          QwordAlignedPropertyBufferLength;
  ULONG                          PropertyBufferLength;
  ULONG                          PropertyBufferOffset;
} NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO, *PNDIS_SWITCH_PORT_PROPERTY_ENUM_INFO;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  




### -field NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PropertyVersion

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the property for the extensible switch port. 


### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier for the extensible switch port property.




### -field QwordAlignedPropertyBufferLength

A ULONG value that specifies the aligned size, in bytes, of the property buffer.


### -field PropertyBufferLength

A ULONG value that specifies the actual size, in bytes, of the property buffer.

<div class="alert"><b>Note</b>  This value must be less than or equal to the value of the <b>QwordAlignedPropertyBufferLength</b> member.</div>
<div> </div>

### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer that follows the <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure. The offset is measured from the start of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure up to the beginning of the property buffer.


## -remarks
The <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598277">OID_SWITCH_PORT_PROPERTY_ENUM</a>. An array of <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structures follow the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_enum_parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a> structure in the information buffer that is associated with this OID request. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access the next <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> element that follows an <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure in the array  by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598234">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT</a> macro.

Extensible switch extensions can access the port property buffer that is specified by an <b>NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</b> structure  by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598235">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_PROPERTY</a> macro.

For more information about extensible switch policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598234">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_NEXT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598235">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO_GET_PROPERTY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_enum_parameters.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598277">OID_SWITCH_PORT_PROPERTY_ENUM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

