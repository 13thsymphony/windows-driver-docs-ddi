---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
title: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_PORT_CONTROLLER_CONFIG structure.
old-location: buses\ucmtcpci_port_controller_config_init.htm
old-project: usbref
ms.assetid: 8e9718e1-2f7c-4322-a34d-2faa45f4f97e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT, UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT method [Buses], buses.ucmtcpci_port_controller_config_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
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
-	UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---


# UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function
Initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.

## Syntax

```
void UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT(
  PUCMTCPCI_PORT_CONTROLLER_CONFIG         Config,
  PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification,
  PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES   Capabilities
);
```

## Parameters

`Config`

A pointer to the driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.

`Identification`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805879">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.

`Capabilities`

A pointer to the 
                 <a href="https://msdn.microsoft.com/library/windows/hardware/mt805870">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>