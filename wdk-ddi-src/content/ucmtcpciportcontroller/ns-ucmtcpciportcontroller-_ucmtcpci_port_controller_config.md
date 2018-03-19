---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_CONFIG
title: "_UCMTCPCI_PORT_CONTROLLER_CONFIG"
author: windows-driver-content
description: Contains configuration options for the port controller object, passed by the client driver in the call to UcmTcpciPortControllerCreate. Call UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_config.htm
old-project: usbref
ms.assetid: a9027cda-0851-46e2-9006-0d757109fc3a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_CONFIG, PUCMTCPCI_PORT_CONTROLLER_CONFIG, PUCMTCPCI_PORT_CONTROLLER_CONFIG structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_CONFIG, UCMTCPCI_PORT_CONTROLLER_CONFIG structure [Buses], _UCMTCPCI_PORT_CONTROLLER_CONFIG, buses.ucmtcpci_port_controller_config, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_CONFIG, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontroller.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_CONFIG
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_CONFIG, *PUCMTCPCI_PORT_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_CONFIG structure
Contains configuration options for the port controller object,  passed by the client driver in the call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>. Call <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpci_port_controller_config_init.md">UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</a> to initialize this structure.

## Syntax
````
typedef struct _UCMTCPCI_PORT_CONTROLLER_CONFIG {
  ULONG                                    Size;
  PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification;
  PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES   Capabilities;
} UCMTCPCI_PORT_CONTROLLER_CONFIG, *PUCMTCPCI_PORT_CONTROLLER_CONFIG;
````

## Members


`Size`

Size of this structure.

`Identification`

A pointer to the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification.md">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.

`Capabilities`

A pointer to the 
                 <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_capabilities.md">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontroller.h |

## See Also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>