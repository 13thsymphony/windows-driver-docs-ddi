---
UID: NS:ucxroothub._ROOTHUB_20PORT_INFO
title: "_ROOTHUB_20PORT_INFO"
author: windows-driver-content
description: Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function.
old-location: buses\_roothub_20port_info.htm
old-project: usbref
ms.assetid: AA71D015-B047-497C-A9E1-32E5E73AD0C2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PROOTHUB_20PORT_INFO, P_ROOTHUB_20PORT_INFO, P_ROOTHUB_20PORT_INFO structure pointer [Buses], ROOTHUB_20PORT_INFO, ROOTHUB_20PORT_INFO structure [Buses], _ROOTHUB_20PORT_INFO, buses._roothub_20port_info, ucxroothub/P_ROOTHUB_20PORT_INFO, ucxroothub/_ROOTHUB_20PORT_INFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	ROOTHUB_20PORT_INFO
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_20PORT_INFO, *PROOTHUB_20PORT_INFO
req.product: Windows 10 or later.
---

# _ROOTHUB_20PORT_INFO structure
Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187834">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.

## Syntax
```
typedef struct _ROOTHUB_20PORT_INFO {
  USHORT                               PortNumber;
  UCHAR                                MinorRevision;
  UCHAR                                HubDepth;
  TRISTATE                             Removable;
  TRISTATE                             IntegratedHubImplemented;
  TRISTATE                             DebugCapable;
  CONTROLLER_USB_20_HARDWARE_LPM_FLAGS ControllerUsb20HardwareLpmFlags;
} *PROOTHUB_20PORT_INFO, ROOTHUB_20PORT_INFO;
```

## Members


`PortNumber`

The USB 2.0 root hub port number.

`MinorRevision`

Minor revision number.

`HubDepth`

The hub depth limit.

`Removable`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is removable.

`IntegratedHubImplemented`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is implemented.

`DebugCapable`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187907">TRISTATE</a> value that indicates if the port is debug capable.

`ControllerUsb20HardwareLpmFlags`

A value that indicates Link Power Management (LPM) flags for the controller.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxroothub.h (include Ucxclass.h) |