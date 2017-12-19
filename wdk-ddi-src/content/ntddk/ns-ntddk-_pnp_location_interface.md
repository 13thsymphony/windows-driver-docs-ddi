---
UID: NS.NTDDK._PNP_LOCATION_INTERFACE
title: _PNP_LOCATION_INTERFACE
author: windows-driver-content
description: The PNP_LOCATION_INTERFACE structure describes the GUID_PNP_LOCATION_INTERFACE interface.
old-location: kernel\pnp_location_interface.htm
old-project: kernel
ms.assetid: 5189ffad-e5dc-4f5a-a7e3-481d36332c81
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PNP_LOCATION_INTERFACE, *PPNP_LOCATION_INTERFACE, PNP_LOCATION_INTERFACE, PPNP_LOCATION_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows Server 2003 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PNP_LOCATION_INTERFACE
req.alt-loc: Ntddk.h
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

# _PNP_LOCATION_INTERFACE structure



## -description
The <b>PNP_LOCATION_INTERFACE</b> structure describes the <a href="kernel.guid_pnp_location_interface">GUID_PNP_LOCATION_INTERFACE</a> interface.



## -syntax

````
typedef struct _PNP_LOCATION_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PGET_LOCATION_STRING   GetLocationString;
} PNP_LOCATION_INTERFACE, *PPNP_LOCATION_INTERFACE;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined version of the interface.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="kernel.interfacereference">InterfaceReference</a> routine that increments the reference count for the interface. The PINTERFACE_REFERENCE function pointer type is defined in the Wdm.h header file.


### -field InterfaceDereference

A pointer to an <a href="kernel.interfacedereference">InterfaceDereference</a> routine that decrements the reference count for the interface. The PINTERFACE_DEREFERENCE function pointer type is defined in the Wdm.h header file.


### -field GetLocationString

A pointer to the <a href="..\ntddk\nc-ntddk-pget_location_string.md">PnpGetLocationString</a> routine for the interface. The routine supplies the device-specific part of the SPDRP_LOCATION_PATHS property for the device.


## -remarks
A driver obtains a pointer to the <b>PNP_LOCATION_INTERFACE</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to GUID_PNP_LOCATION_INTERFACE.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows Server 2003 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.interfacedereference">InterfaceDereference</a>
</dt>
<dt>
<a href="kernel.interfacereference">InterfaceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pget_location_string.md">PnpGetLocationString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PNP_LOCATION_INTERFACE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

