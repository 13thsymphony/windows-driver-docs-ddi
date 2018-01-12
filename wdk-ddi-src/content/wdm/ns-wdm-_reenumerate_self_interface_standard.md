---
UID: NS:wdm._REENUMERATE_SELF_INTERFACE_STANDARD
title: _REENUMERATE_SELF_INTERFACE_STANDARD
author: windows-driver-content
description: The REENUMERATE_SELF_INTERFACE_STANDARD interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure defines the GUID_REENUMERATE_SELF_INTERFACE_STANDARD interface.
old-location: kernel\reenumerate_self_interface_standard.htm
old-project: kernel
ms.assetid: f44a57e9-4536-46a7-a80e-d4bbbb2a9ad5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _REENUMERATE_SELF_INTERFACE_STANDARD, *PREENUMERATE_SELF_INTERFACE_STANDARD, REENUMERATE_SELF_INTERFACE_STANDARD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REENUMERATE_SELF_INTERFACE_STANDARD
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PREENUMERATE_SELF_INTERFACE_STANDARD, REENUMERATE_SELF_INTERFACE_STANDARD
req.product: Windows 10 or later.
---

# _REENUMERATE_SELF_INTERFACE_STANDARD structure



## -description
The <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure  defines the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546570">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a> interface.



## -syntax

````
typedef struct _REENUMERATE_SELF_INTERFACE_STANDARD {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PREENUMERATE_SELF      SurpriseRemoveAndReenumerateSelf;
} REENUMERATE_SELF_INTERFACE_STANDARD, *PREENUMERATE_SELF_INTERFACE_STANDARD;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SurpriseRemoveAndReenumerateSelf

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560837">ReenumerateSelf</a> routine that requests device reenumeration.


## -remarks
A driver obtains a pointer to the <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to GUID_REENUMERATE_SELF_INTERFACE_STANDARD.

The <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> structure is an extension of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546570">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560837">ReenumerateSelf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REENUMERATE_SELF_INTERFACE_STANDARD structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

