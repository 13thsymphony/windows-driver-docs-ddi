---
UID: NS:ucxroothub._ROOTHUB_20PORT_INFO
title: "_ROOTHUB_20PORT_INFO"
author: windows-driver-content
description: Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function.
old-location: buses\_roothub_20port_info.htm
old-project: usbref
ms.assetid: AA71D015-B047-497C-A9E1-32E5E73AD0C2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ROOTHUB_20PORT_INFO, ucxroothub/P_ROOTHUB_20PORT_INFO, P_ROOTHUB_20PORT_INFO, _ROOTHUB_20PORT_INFO, ROOTHUB_20PORT_INFO structure [Buses], buses._roothub_20port_info, P_ROOTHUB_20PORT_INFO structure pointer [Buses], ucxroothub/_ROOTHUB_20PORT_INFO, *PROOTHUB_20PORT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxroothub.h
apiname:
-	ROOTHUB_20PORT_INFO
product: Windows
targetos: Windows
req.typenames: "*PROOTHUB_20PORT_INFO, ROOTHUB_20PORT_INFO"
req.product: Windows 10 or later.
---

# _ROOTHUB_20PORT_INFO structure
Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_20port_info.md">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.

## Syntax
````
typedef struct _ROOTHUB_20PORT_INFO {
  USHORT                               PortNumber;
  UCHAR                                MinorRevision;
  UCHAR                                HubDepth;
  TRISTATE                             Removable;
  TRISTATE                             IntegratedHubImplemented;
  TRISTATE                             DebugCapable;
  CONTROLLER_USB_20_HARDWARE_LPM_FLAGS ControllerUsb20HardwareLpmFlags;
} ROOTHUB_20PORT_INFO, *P_ROOTHUB_20PORT_INFO;
````

## Members


`ControllerUsb20HardwareLpmFlags`

A value that indicates Link Power Management (LPM) flags for the controller.

`DebugCapable`

A <a href="..\ucxroothub\ne-ucxroothub-_tristate.md">TRISTATE</a> value that indicates if the port is debug capable.

`HubDepth`

The hub depth limit.

`IntegratedHubImplemented`

A <a href="..\ucxroothub\ne-ucxroothub-_tristate.md">TRISTATE</a> value that indicates if the port is implemented.

`MinorRevision`

Minor revision number.

`PortNumber`

The USB 2.0 root hub port number.

`Removable`

A <a href="..\ucxroothub\ne-ucxroothub-_tristate.md">TRISTATE</a> value that indicates if the port is removable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxroothub.h (include Ucxclass.h) |