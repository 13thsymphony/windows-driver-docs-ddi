---
UID: NS.FWPSK._NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
title: _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure specifies the parameters for a policy property of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_parameters.htm
old-project: netvista
ms.assetid: 656acfd4-6f34-41aa-862e-134a2b95dcab
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_PORT_PROPERTY_PARAMETERS
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
req.irql: <= DISPATCH_LEVEL
---

# _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure



## -description
The <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure specifies the parameters for a policy property of a Hyper-V extensible switch port. 



## -syntax

````
typedef struct _NDIS_SWITCH_PORT_PROPERTY_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_PORT_ID                      PortId;
  NDIS_SWITCH_PORT_PROPERTY_TYPE           PropertyType;
  NDIS_SWITCH_OBJECT_ID                    PropertyId;
  NDIS_SWITCH_OBJECT_VERSION               PropertyVersion;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  NDIS_SWITCH_OBJECT_INSTANCE_ID           PropertyInstanceId;
  ULONG                                    PropertyBufferLength;
  ULONG                                    PropertyBufferOffset;
  ULONG                                    Reserved;
} NDIS_SWITCH_PORT_PROPERTY_PARAMETERS, *PNDIS_SWITCH_PORT_PROPERTY_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:




### -field NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field PortId

 An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the property is assigned.


### -field PropertyType

 An <a href="netvista.ndis_switch_port_property_type">NDIS_SWITCH_PORT_PROPERTY_TYPE</a> enumeration value that specifies the type of port property that is contained within the property buffer.


### -field PropertyId

A GUID value that identifies the property for the extensible switch port.

For more information, see the Remarks section.

<div class="alert"><b>Note</b>  The extensible switch extension must ignore this member unless the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeCustom</b>.</div>
<div> </div>

### -field PropertyVersion

An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the property for the extensible switch port.




### -field SerializationVersion

An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized port property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that identifies the instance of the  property for the extensible switch port.




### -field PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the property buffer.


### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer that follows the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure up to the beginning of the property buffer. 


### -field Reserved

Reserved for future use.


## -remarks
The <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure is used in the following OID set requests:


<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


The property buffer contains a structure that is associated with the <b>PropertyType</b> member. The property buffer follows the <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

The extensible switch extension must follow these guidelines when it processes an <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure:

If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeSecurity</b>, the property buffer is formatted as an <a href="netvista.ndis_switch_port_property_security">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a> structure.

If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeVlan</b>, the property buffer is formatted as an <a href="netvista.ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a> structure.

If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeProfile</b>, the property buffer is formatted as an <a href="netvista.ndis_switch_port_property_profile">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a> structure.

If the <b>PropertyType</b> member is set to <b>NdisSwitchPortPropertyTypeCustom</b>, the <b>PropertyId</b> member must be set to the GUID value the independent software vendor (ISV) created for the custom port property. The property buffer is formatted as a <a href="netvista.ndis_switch_port_property_custom">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a> structure that contains the parameters for the custom port property as defined by the ISV.

Extensible switch extensions can access the custom port property inside an <b>NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598239">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY</a> macro.

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
<dt>Ntddndis.h (include Ndis.h or Fwpsk.h)</dt>
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
<a href="netvista.ndis_switch_port_property_custom">NDIS_SWITCH_PORT_PROPERTY_CUSTOM</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598239">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS_GET_PROPERTY</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_profile">NDIS_SWITCH_PORT_PROPERTY_PROFILE</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_security">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_type">NDIS_SWITCH_PORT_PROPERTY_TYPE</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_vlan">NDIS_SWITCH_PORT_PROPERTY_VLAN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_PARAMETERS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

