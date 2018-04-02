---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS"
author: windows-driver-content
description: Stores information about the pin assignment of the DisplayPort alternate mode that was configured. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED request.
old-location: buses\ucmtcpci_port_controller_displayport_configured_in_params.htm
old-project: usbref
ms.assetid: 91672EF6-3795-4DE1-9C7B-76E68490D0E6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, buses.ucmtcpci_port_controller_displayport_configured_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmtcpciportcontrollerrequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure
Stores information about the  pin assignment of the DisplayPort alternate mode that was configured. This structure is used in the 
             <a href="https://msdn.microsoft.com/library/windows/hardware/mt805830">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a>  request.

## Syntax
```
typedef struct _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                              PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_PIN_ASSIGNMENT PinAssignment;
} *PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS;
```

## Members


`PortControllerObject`

Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.

`PinAssignment`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt805902">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_PIN_ASSIGNMENT</a>-type value that indicates the pin that was configured.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt805830">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a>