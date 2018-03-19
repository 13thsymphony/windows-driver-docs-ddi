---
UID: NS:ntddndis._NDIS_SWITCH_PROPERTY_ENUM_INFO
title: "_NDIS_SWITCH_PROPERTY_ENUM_INFO"
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_ENUM_INFO structure specifies information about a profile property for the Hyper-V extensible switch.
old-location: netvista\ndis_switch_property_enum_info.htm
old-project: netvista
ms.assetid: 1b990bc5-3ff4-4e37-b011-258c4dbe8f22
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SWITCH_PROPERTY_ENUM_INFO, NDIS_SWITCH_PROPERTY_ENUM_INFO, NDIS_SWITCH_PROPERTY_ENUM_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PROPERTY_ENUM_INFO, PNDIS_SWITCH_PROPERTY_ENUM_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PROPERTY_ENUM_INFO, netvista.ndis_switch_property_enum_info, ntddndis/NDIS_SWITCH_PROPERTY_ENUM_INFO, ntddndis/PNDIS_SWITCH_PROPERTY_ENUM_INFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PROPERTY_ENUM_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PROPERTY_ENUM_INFO, *PNDIS_SWITCH_PROPERTY_ENUM_INFO
---

# _NDIS_SWITCH_PROPERTY_ENUM_INFO structure
The <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure specifies information about a profile property for the Hyper-V extensible switch.

## Syntax
````
typedef struct _NDIS_SWITCH_PROPERTY_ENUM_INFO {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_SWITCH_OBJECT_INSTANCE_ID PropertyInstanceId;
  NDIS_SWITCH_OBJECT_VERSION     PropertyVersion;
  ULONG                          QwordAlignedPropertyBufferLength;
  ULONG                          PropertyBufferLength;
  ULONG                          PropertyBufferOffset;
} NDIS_SWITCH_PROPERTY_ENUM_INFO, *PNDIS_SWITCH_PROPERTY_ENUM_INFO;
````

## Members


`Header`

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PROPERTY_ENUM_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1.

`Flags`

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

`PropertyInstanceId`

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier of the  extensible switch property.

`PropertyVersion`

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the property for the extensible switch port.

`QwordAlignedPropertyBufferLength`

A ULONG value that specifies the aligned size, in bytes, of the property buffer.

`PropertyBufferLength`

A ULONG value that specifies the actual size, in bytes, of the property buffer.

<div class="alert"><b>Note</b>  This value must be less than or equal to the value of the <b>QwordAlignedPropertyBufferLength</b> member.</div>
<div> </div>

`PropertyBufferOffset`

A ULONG value that specifies the offset, in bytes, to the property buffer that follows the <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure. The offset is measured from the start of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_parameters.md">NDIS_SWITCH_PROPERTY_PARAMETERS</a> structure up to the beginning of the property buffer.

## Remarks
The <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>. An array of <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structures follows the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_enum_parameters.md">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access the next <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> element that follows an <b>NDIS_SWITCH_PROPERTY_ENUM_INFO</b> structure in the array  by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598251">NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_NEXT</a> macro.

Extensible switch extensions can access the extensible switch property buffer that is specified by an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_enum_info.md">NDIS_SWITCH_PORT_PROPERTY_ENUM_INFO</a> structure  by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598252">NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY</a> macro.

For more information about extensible switch policies, see <a href="https://msdn.microsoft.com/8AB85E48-EF37-4D42-873B-34D4835AF22E">Hyper-V Extensible Switch Policies</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598251">NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_NEXT</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_property_enum_parameters.md">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598252">NDIS_SWITCH_PROPERTY_ENUM_INFO_GET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<b></b>