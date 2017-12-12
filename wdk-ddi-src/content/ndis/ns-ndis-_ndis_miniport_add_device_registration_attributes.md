---
UID: NS.NDIS._NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
title: _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
author: windows-driver-content
description: The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context area for an added device.
old-location: netvista\ndis_miniport_add_device_registration_attributes.htm
old-project: netvista
ms.assetid: 7e8b5dbf-2d56-4278-8953-8e21ba1cee06
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure



## -description
The NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure specifies a driver-defined context
  area for an added device.



## -syntax

````
typedef struct _NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES {
  NDIS_OBJECT_HEADER Header;
  NDIS_HANDLE        MiniportAddDeviceContext;
  ULONG              Flags;
} NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES_REVISION_1.


### -field MiniportAddDeviceContext

A handle for a driver-allocated context area.


### -field Flags

Reserved.


## -remarks
Miniport drivers initialize an NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure in the 
    <a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a> function and pass
    this structure to the 
    <a href="netvista.ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function.

NDIS later passes the context handle in the 
    <b>MiniportAddDeviceContext</b> member of NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES to the 
    <i>MiniportAddDeviceContext</i> parameter of the 
    <a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>, 
    <a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>, and 
    <a href="netvista.miniportfilterresourcerequirements">
    MiniportFilterResourceRequirements</a> functions. NDIS passes the same handle to the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function in
    the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="netvista.ndis_miniport_init_parameters">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_add_device.md">MiniportAddDevice</a>
</dt>
<dt>
<a href="netvista.miniportfilterresourcerequirements">
   MiniportFilterResourceRequirements</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_remove_device.md">MiniportRemoveDevice</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_pnp_irp.md">MiniportStartDevice</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

