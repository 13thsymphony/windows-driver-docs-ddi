---
UID: NS.NTDDNDIS._NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
title: _NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure specifies an array of profile properties for the Hyper-V extensible switch. Each element in the array is formatted as an NDIS_SWITCH_PROPERTY_ENUM_INFO structure.
old-location: netvista\ndis_switch_property_enum_parameters.htm
old-project: NetVista
ms.assetid: f133f6cc-6e09-4eb8-b6fe-50d207391621
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, *PNDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, PNDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
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
req.alt-api: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
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
---

# _NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure



## -description
The <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure specifies an array of profile properties for the Hyper-V extensible switch. Each element in the array is formatted as an <a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structure.



## -syntax

````
typedef struct _NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_PROPERTY_TYPE                PropertyType;
  NDIS_SWITCH_OBJECT_ID                    PropertyId;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  ULONG                                    FirstPropertyOffset;
  ULONG                                    NumProperties;
} NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, *PNDIS_SWITCH_PROPERTY_ENUM_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:




### -field NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PropertyType

 An <a href="netvista.ndis_switch_property_type">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration value that specifies the extensible switch property type. When an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a> is issued, the extensible switch extension returns extensible switch properties that match this property type.


### -field PropertyId

A GUID value that identifies the extensible switch property.




### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized extensible switch property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field FirstPropertyOffset

A USHORT value that specifies the offset, in bytes, to the first <a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> element that follows the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure up to the beginning of the first element in the array.

<div class="alert"><b>Note</b>  If the value of <b>NumProperties</b> is zero, this member is ignored. </div>
<div> </div>

### -field NumProperties

A ULONG value that specifies the number of <a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> elements that follow the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. 


## -remarks
The <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>. An array of <a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structures follows the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access the first <a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structure that is specified by the  <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598254">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO</a> macro.

For more information about extensible switch policies, see <a href="netvista.hyper_v_extensible_switch_policies">Hyper-V Extensible Switch Policies</a>.


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
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndis_switch_property_enum_info">NDIS_SWITCH_PROPERTY_ENUM_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

