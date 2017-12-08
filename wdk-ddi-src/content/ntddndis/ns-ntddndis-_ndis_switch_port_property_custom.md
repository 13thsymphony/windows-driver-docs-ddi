---
UID: NS.NTDDNDIS._NDIS_SWITCH_PORT_PROPERTY_CUSTOM
title: _NDIS_SWITCH_PORT_PROPERTY_CUSTOM
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure specifies a custom policy property for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_custom.htm
old-project: netvista
ms.assetid: 5ac17c34-c71c-45a7-870f-7e135c8bd5ca
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_SWITCH_PORT_PROPERTY_CUSTOM, *PNDIS_SWITCH_PORT_PROPERTY_CUSTOM, NDIS_SWITCH_PORT_PROPERTY_CUSTOM
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
req.alt-api: NDIS_SWITCH_PORT_PROPERTY_CUSTOM
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

# _NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure



## -description

The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure specifies a custom policy property for a Hyper-V extensible switch port. 
Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV.

The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure specifies a custom policy property for a Hyper-V extensible switch port. 
Independent software vendors (ISVs) define the format for the custom properties. The format of the custom property is proprietary to the ISV.


## -syntax

````
typedef struct _NDIS_SWITCH_PORT_PROPERTY_CUSTOM {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              PropertyBufferLength;
  ULONG              PropertyBufferOffset;
} NDIS_SWITCH_PORT_PROPERTY_CUSTOM, *PNDIS_SWITCH_PORT_PROPERTY_CUSTOM;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  


### -field NDIS_SWITCH_PORT_PROPERTY_CUSTOM_REVISION_1

Original version for NDIS 6.30 and later.
Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_CUSTOM_REVISION_1.
</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field PropertyBufferLength

A ULONG value that specifies the size, in bytes, of the buffer that contains the custom port property.

### -field PropertyBufferOffset

A ULONG value that specifies the offset, in bytes, to the property buffer. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure up to the beginning of the property buffer.

## -remarks
The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure is used in the following OID set requests: 


<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


The <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure follows the <a href="netvista.ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

Extensible switch extensions can access the custom port property buffer inside an <b>NDIS_SWITCH_PORT_PROPERTY_CUSTOM</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598231">NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER</a> macro.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598231">NDIS_SWITCH_PORT_PROPERTY_CUSTOM_GET_BUFFER</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PROPERTY_CUSTOM structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
