---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
title: "_UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION"
author: windows-driver-content
description: Contains identification information and USB specification version information (in BCD format) about the port controller.
old-location: buses\ucmtcpci_port_controller_identification.htm
old-project: usbref
ms.assetid: fad8ca8b-1854-4a71-a0f2-60c211ece022
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure [Buses], _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, buses.ucmtcpci_port_controller_identification, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION"
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
-	UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure
Contains identification information and USB specification version information (in BCD format) about the port controller.
             This client driver must specify that information in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a> during initialization. 
                 Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt805880">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT</a> to initialize this structure.

## Syntax
```
typedef struct _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION {
  ULONG  Size;
  UINT16 VendorId;
  UINT16 ProductId;
  UINT16 DeviceId;
  UINT16 TypeCRevisionInBcd;
  UINT16 PDRevisionAndVersionInBcd;
  UINT16 PDInterfaceRevisionAndVersionInBcd;
} *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION;
```

## Members


`Size`

Size of this structure.

`VendorId`

Specifies the vendor identifier assigned by the USB specification committee.

`ProductId`

Specifies the product identifier. This value is assigned by the manufacturer.

`DeviceId`

The device ID for the USB Type-C port  controller.

`TypeCRevisionInBcd`

The revision ID for the USB Type-C port  controller.

`PDRevisionAndVersionInBcd`

The revision and version for the USB Type-C port  controller that supports PD.

`PDInterfaceRevisionAndVersionInBcd`

The interface revision and version for the USB Type-C port  controller that supports PD.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontroller.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>