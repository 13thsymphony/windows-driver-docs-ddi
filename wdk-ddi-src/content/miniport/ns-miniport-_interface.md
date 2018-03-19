---
UID: NS:miniport._INTERFACE
title: "_INTERFACE"
author: windows-driver-content
description: The INTERFACE structure describes an interface that is exported by a driver for use by other drivers.
old-location: kernel\interface.htm
old-project: kernel
ms.assetid: d853643d-d3e8-40cc-a8a8-848f36f3bdae
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PINTERFACE, INTERFACE, INTERFACE structure [Kernel-Mode Driver Architecture], PINTERFACE, PINTERFACE structure pointer [Kernel-Mode Driver Architecture], _INTERFACE, kernel.interface, kstruct_b_667d57fa-a959-4904-a15e-af4d4f44988e.xml, wdm/INTERFACE, wdm/PINTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	INTERFACE
product: Windows
targetos: Windows
req.typenames: INTERFACE, *PINTERFACE
---

# _INTERFACE structure
The <b>INTERFACE</b> structure describes an interface that is exported by a driver for use by other drivers.

## Syntax
````
typedef struct _INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
} INTERFACE, *PINTERFACE;
````

## Members


`Size`

Size, in bytes, of a structure defining a driver interface, including this structure and interface-specific members.

`Version`

Driver-defined interface version.

`Context`

Pointer to interface-specific context information.

`InterfaceReference`

Pointer to a driver-supplied <a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a> routine that increments the interface's reference count.

`InterfaceDereference`

Pointer to a driver-supplied <a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a> routine that decrements the interface's reference count.

## Remarks
The <b>INTERFACE</b> structure must be included as the first member of all structures that describe interfaces returned by drivers in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request.

The <i>InterfaceReference</i> routine must be called by the driver that exports the interface, each time the driver supplies that interface in response to <b>IRP_MN_QUERY_INTERFACE</b>. Likewise, if the driver that requests the interface subsequently passes it to another driver, the driver that passes the interface must call <i>InterfaceReference</i> on behalf of the driver that receives it.

Each driver that imports the interface (whether by sending <b>IRP_MN_QUERY_INTERFACE</b> or by receiving the interface from another driver) must call the <i>InterfaceDereference</i> routine after it has finished using the interface. After calling the <i>InterfaceDereference</i> routine, a driver cannot use the interface again without first reobtaining it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |

## See Also

<a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a>



<a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>