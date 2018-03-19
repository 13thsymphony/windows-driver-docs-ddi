---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
author: windows-driver-content
description: Stores the values of all status registers of the port controller. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location: buses\ucmtcpci_port_controller_get_status_out_params.htm
old-project: usbref
ms.assetid: e43b2a10-20b5-4cb8-ae7b-fc1feb7a4bf1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, buses.ucmtcpci_port_controller_get_status_out_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
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
-	UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure
Stores the values of all status registers of the port controller. This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.

## Syntax
````
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS {
  UCMTCPCI_PORT_CONTROLLER_CC_STATUS    CCStatus;
  UCMTCPCI_PORT_CONTROLLER_POWER_STATUS PowerStatus;
  UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS FaultStatus;
} UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS;
````

## Members


`CCStatus`

A 
                 <b>UCMTCPCI_PORT_CONTROLLER_CC_STATUS</b> structure that describes the CC_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

`PowerStatus`

A 
                 <b>UCMTCPCI_PORT_CONTROLLER_POWER_STATUS</b> structure that describes the POWER_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

`FaultStatus`

A 
                 <b>UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS</b> structure that describes the FAULT_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>