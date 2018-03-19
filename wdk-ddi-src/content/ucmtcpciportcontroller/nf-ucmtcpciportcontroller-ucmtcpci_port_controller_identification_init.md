---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
title: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure.
old-location: buses\ucmtcpci_port_controller_identification_init.htm
old-project: usbref
ms.assetid: 4204b849-8195-4a1b-9bb3-1e9cbeb12223
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT method [Buses], buses.ucmtcpci_port_controller_identification_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---


# UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function
Initializes the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification.md">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.

## Syntax

````
VOID UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT(
  _Out_ PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification
);
````

## Parameters

`Identification`

A pointer to the driver-allocated <b>UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</b> structure.


## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ucmtcpciportcontroller.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>