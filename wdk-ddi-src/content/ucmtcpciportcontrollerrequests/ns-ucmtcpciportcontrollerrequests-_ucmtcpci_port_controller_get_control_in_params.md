---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS"
author: windows-driver-content
description: This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_get_control_in_params.htm
old-project: usbref
ms.assetid: 93581775-f523-4e3b-bd90-13ad6e12480e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, buses.ucmtcpci_port_controller_get_control_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS"
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
-	UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure
This structure is used in the 
             <a href="https://msdn.microsoft.com/library/windows/hardware/mt805832">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>  request.

## Syntax
```
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER PortControllerObject;
} *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS;
```

## Members


`PortControllerObject`

Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt805832">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>