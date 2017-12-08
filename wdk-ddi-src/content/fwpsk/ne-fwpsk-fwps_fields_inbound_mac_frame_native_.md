---
UID: NE.fwpsk.FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
title: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
author: windows-driver-content
description: The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE run-time filtering layer.
old-location: netvista\fwps_fields_inbound_mac_frame_native.htm
old-project: netvista
ms.assetid: 0EFD49D5-1A5D-4D8F-AA19-7A1562C4B581
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_, FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
req.alt-loc: fwpsk.h
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

# FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_ enumeration



## -description
The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.


## -syntax

````
typedef enum  { 
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS,
  FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX
} FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE;
````


## -enum-fields

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE

The inbound MAC frame native NDIS media type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE

The inbound MAC frame native NDIS physical media type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE

The inbound MAC frame native interface field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE

The inbound MAC frame native interface type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX

The inbound MAC frame native interface index field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT

The inbound MAC frame native NDIS port field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS

The inbound MAC frame native flags field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>